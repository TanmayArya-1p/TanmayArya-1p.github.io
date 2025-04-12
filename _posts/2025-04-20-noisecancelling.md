---
layout: post
title: "Frequency-Domain Noise Cancellation Using Threshold Filtering"
date: 2025-04-12 19:22:59 +0000
categories: [Projects]
toc: false
---


- Original Audio Sample: 

- Noisy Audio Sample:

- Denoised Audio Sample:



#### Script for Threshold Filtering:

```py
import sounddevice as sd
import numpy as np
import matplotlib.pyplot as plt
from scipy.io.wavfile import write

class ThresholdFilter:
    def __init__(self, rate=44100, time=4, thresh=0.1, freq_limit=10000, freq_step=500):
        self.rate = rate
        self.time = time
        self.thresh = thresh
        self.freq_limit = freq_limit
        self.freq_step = freq_step

    def record(self):
        print(f"[RECORD] Recording for {self.time} seconds")
        audio = sd.rec(int(self.time * self.rate), samplerate=self.rate, channels=1, dtype='float32')
        sd.wait()
        print("[RECORD] Done Recording")
        return np.squeeze(audio)

    def plot_fft(self, sig, title="FFT"):
        n = len(sig)
        fft = np.fft.fft(sig)
        freqs = np.fft.fftfreq(n, 1 / self.rate)

        pos = freqs >= 0
        x = freqs[pos]
        y = np.abs(fft[pos])

        plt.figure(figsize=(12, 6))
        plt.plot(x, y)
        plt.title(title)
        plt.xlabel("Freq (Hz)")
        plt.ylabel("Magnitude")
        plt.grid(True)

        lim = min(self.freq_limit, self.rate // 2)
        plt.xlim(0, lim)

        ticks = np.arange(0, lim + self.freq_step, self.freq_step)
        plt.xticks(ticks, rotation=45, ha='right')
        plt.tight_layout()

        return fft, freqs

    def clean_fft(self, fft):
        clean = fft.copy()
        max_val = np.max(np.abs(clean))
        thresh_val = self.thresh * max_val

        print(f"[THRESHOLDING] Thresholding with : {thresh_val:.2f}")
        clean[np.abs(clean) < thresh_val] = 0

        zeroed = np.sum(np.abs(clean) == 0)
        total = len(clean)
        print(f"[THRESHOLDING] Zeroed {zeroed}/{total} components ({100 * zeroed / total:.2f}%)")

        return clean

    def toTimeDomain(self, clean_fft):
        return np.real(np.fft.ifft(clean_fft))

    def play(self, sig):
        print("[PLAYER] Playing...")
        sd.play(sig.astype(np.float32), self.rate)
        sd.wait()
        print("[PLAYER] Done.")

    def save_audio(self, name, sig):
        norm = np.int16(sig / np.max(np.abs(sig)) * 32767)
        write(name, self.rate, norm)
        print(f"[SAVER] Saved to '{name}'")

    def run(self):
        audio = self.record()
        self.save_audio("input_audio.wav", audio)

        print("[MAIN] Plotting Original FFT")
        fft_orig, freqs = self.plot_fft(audio, title=f"Original FFT (0-{self.freq_limit} Hz)")

        print("[THRESHOLDING] Started thresholding")
        fft_clean = self.clean_fft(fft_orig)
        print("[THRESHOLDING] Finished thresholding")

        print("[MAIN] Plotting Denoised FFT")
        pos = freqs >= 0
        x = freqs[pos]
        y_clean = np.abs(fft_clean[pos])

        plt.figure(figsize=(12, 6))
        plt.plot(x, y_clean)
        plt.title(f"Cleaned FFT (0-{self.freq_limit} Hz)")
        plt.xlabel("Freq (Hz)")
        plt.ylabel("Magnitude")
        plt.grid(True)
        plt.xlim(0, min(self.freq_limit, self.rate // 2))
        ticks = np.arange(0, self.freq_limit + self.freq_step, self.freq_step)
        plt.xticks(ticks, rotation=45, ha='right')
        plt.tight_layout()

        print("[MAIN] Performing Inverse FFT")
        audio_clean = self.toTimeDomain(fft_clean)

        print("[MAIN] Playing Clean Audio")
        self.play(audio_clean)
        self.save_audio("denoised.wav", audio_clean)

        plt.show()


if __name__ == "__main__":
    tf = ThresholdFilter()
    tf.run()

```