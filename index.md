---
layout: page
# Index page
---

<h1> Hi, I'm <b>Tanmay Arya</b>. <br>
<h4>I'm currently doing a CS undergrad at IIT Roorkee.</h4> </h1>
<html>
<video
  id="bg-video"
  autoplay
  muted
  loop
  playsinline
>
  <source src="./assets/vid/fluid1.mp4" type="video/mp4">
</video>

<style>
  #bg-video {
    position: fixed;
    top: 0;
    left: 0;
    width: 150vw;
    height: 150vh;
    object-fit: cover;
    z-index: -1;
    opacity: 0.06;          
    pointer-events: none; 
  }

  #bg-video video {
  width: 100%;
  height: 100%;
  object-fit: contain;      /* IMPORTANT: avoids upscaling */
}

footer, header {
  background: transparent !important;
}
</style>

<script>
  const v = document.getElementById("bg-video");
  v.playbackRate = 2;
</script>
</html>

## About Me

My interests keep changing, but I have a soft spot for Systems Programming and DevOps.
I like to learn about how computers work, and I enjoy tinkering with software.

I primarily code in <span style="color: #CE412B;">**Rust**</span>, <span style="color: #00599C;">**C++**</span>, <span style="color: #00ADD8;">**GoLang**</span>, and <span style="color: #3776AB;">**Python**</span>.

I'm also a member of [SDSLabs](https://sdslabs.co).

*BTW the background of this page is a [smoke simulation I wrote.](https://github.com/TanmayArya-1p/fluidsim-cpp)*

## Contact Me

You can find me on [GitHub](https://github.com/TanmayArya-1p) and [LinkedIn](https://www.linkedin.com/in/tanmayarya/).
You can also reach out to me by email at [tanmay[at]onetincan[dot]foo](mailto:tanmay@onetincan.foo) or [tanmayarya2018[at]gmail[dot]com](mailto:tanmayarya2018@gmail.com) *(Primary)*

If all else fails then you can contact me on [Signal](https://signal.me/#eu/1pWMAtPH8gFirUgWn5QQu57NNG9zHFdoGmKZ6cX952v9Tp2EaOpMU7TJAC4huU-Y)

## Open Source Contributions

I like to contribute to open source projects, mostly through small fixes but I try on bigger ones as well.

Here is a list of my contributions to open source projects:

- [Validate target Source Paths in the Cargo build system](https://github.com/rust-lang/cargo/pull/16338)


- [Display lockfile path when Cargo blocks on a build.](https://github.com/rust-lang/cargo/pull/16491)


## Hosted Services You Might Find Useful

- [iitr-ics](https://onetincan.foo/iitr-ics) - Parse out and host an ICal file for the IIT Roorkee Timetable.
- [CPSched API](https://cpsched-api.onetincan.foo) - An API to fetch upcoming CP contests from various platforms.

**PS: Kittens will die if you abuse these services.**


## A reward for scrolling this far!
Thank you for taking the time to acknowledge my existence. I hope you found something interesting on this page.
As a reward, here's a random xkcd comic just for you.

<img src="https://random-xkcder.vercel.app/" title="xkcd" alt="Please Refresh if the comic isn't showing up">



***FYI: my domain keeps changing, so if you find that the any of the links on this page are broken, please let me know!***
