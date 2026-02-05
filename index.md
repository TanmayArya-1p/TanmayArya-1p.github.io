---
layout: page
# Index page
---

Hi, I'm Tanmay Arya, a CS undergrad at IIT Roorkee.
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
    width: 100vw;
    height: 100vh;
    object-fit: cover;
    z-index: -1;
    opacity: 0.25;          
    pointer-events: none; 
  }
</style>

<script>
  const v = document.getElementById("bg-video");
  v.playbackRate = 2;
</script>
</html>
### About Me

My interests keep changing, but I have a soft spot for Systems Programming and DevOps.
I like to learn about how computers work, and I enjoy tinkering with software.

I primarily code in Rust, C++, GoLang, and Python.

I'm also a member of [SDSLabs](https://sdslabs.co).

### Contact Me

You can find me on [GitHub](https://github.com/TanmayArya-1p) and [LinkedIn](https://www.linkedin.com/in/tanmayarya/).
You can also reach out to me at [tanmay[at]onetincan[dot]foo](mailto:tanmay@onetincan.foo)

***FYI: my domain keeps changing, so if you find that the links are broken, please let me know!***


### Open Source Contributions

I like to contribute to open source projects, mostly through small fixes but I try on bigger ones as well.

Here are is a list of my contributions to open source projects:

- [Validate target Source Paths in the Cargo build system](https://github.com/rust-lang/cargo/pull/16338)


- [Display lockfile path when Cargo blocks on a build.](https://github.com/rust-lang/cargo/pull/16491)


### Hosted Services

- [iitr-ics](https://onetincan.foo/iitr-ics) - Parse out and host an ICal file for the IIT Roorkee Timetable.
- [CPSched API](https://cpsched-api.onetincan.foo) - An API to fetch upcoming CP contests from various platforms.


