@title[Introduction]

# Git<span class="gold">Pitch</span>

#### Markdown Presentations For Everyone on Git
<br>
<br>
<span class="byline">[ GitHub, GitLab, Bitbucket, GitBucket, Gitea, Gogs ]</span>

---

@title[PITCHME.md]

#### GitPitch turns <span class="gold">PITCHME.md</span> into
#### interactive,
#### online and offline slideshows.
<br>
<span class="aside">Just like this one...</span>

---

#### No more <span class="gray">Keynote</span>.
#### No more <span class="gray">Powerpoint</span>.
<br>
#### Just <span class="gold">Markdown</span>.
#### Then <span class="gold">Git-Commit</span>.

---?code=assets/md/hello.md&title=Step 1. PITCHME.md

<br>
#### Create slideshow content using GitHub Flavored Markdown in your favorite editor.

<span class="aside">It's as easy as README.md with simple slide-delimeters (---)</span>

---

@title[Step 2. Git-Commit]

### <span class="gold">STEP 2. GIT-COMMIT</span>
<br>

```shell
$ git add PITCHME.md
$ git commit -m "New slideshow content."
$ git push

Done!
```

@[1](Add your PITCHME.md slideshow content file.)
@[2](Commit PITCHME.md to your local repo.)
@[3](Push PITCHME.md to your public repo and you're done!)
@[5](Supports GitHub, GitLab, Bitbucket, GitBucket, Gitea, and Gogs.)

---

@title[Step 3. Done!]

### <span class="gold">STEP 3. GET THE WORD OUT!</span>
<br>
![GitPitch Slideshow URLs](assets/images/gp-slideshow-urls.png)
<br>
<br>
#### Instantly use your GitPitch slideshow URL to promote, pitch or present absolutely anything.

---

@title[Slide Rich]

### <span class="gold">Slide Rich</span>

#### Code Presenting for Blocks, Files, and GISTs
#### Image, Video, Chart, and Math Slides
#### Multiple Themes with Easy Customization
<br>
#### <span class="gold">Plus collaboration is built-in...</span>
#### Your Slideshow is Part of Your Project
#### Under Git Version Control within Your Git Repo

---

@title[Feature Rich]

### <span class="gold">Feature Rich</span>

#### Present Online or Offline
#### With Speaker Notes Support
#### Print Presentation as PDF
#### Auto-Generated Table-of-Contents
#### Share Presentation on Twitter or LinkedIn

---

### <span class="gold">GitPitch Pro - Now Live!</span>

<br>
<div class="left">
    <i class="fa fa-truck fa-5x" aria-hidden="true"> </i><br>
    <a href="https://fontawesome.com/cheatsheet" class="pro-link"> You can use Font Awesome for Icons</a> <br>
    <a href="https://gitpitch.com/pro-features" class="pro-link">
    More details on GitPit Pro here.</a>
</div>
<div class="right">
    <ul>
        <li>Private Repos</li>
        <li>Private URLs</li>
        <li>Password-Protection</li>
        <li>Image Opacity</li>
        <li>SVG Image Support</li>
    </ul>
</div>

---
@title[UEFI Boot Flow]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span></p>


![UEFI Boot Execution Flow](/assets/images/bootflow.JPG)

<!--- comment this does not work
<p>
<img src=https://github.com/Laurie0131/PitchSample/blob/master/assets/images/bootflow.JPG width="425"/></p>
-->

<p align="center"><span style="color:gray; font-size:0.5em"> <b>UEFI Boot Execution Flow</b> </span>

---
@title[UEFI Boot Flow Sec]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>SEC</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg4.png =10x)


Note:
SEC Function <Br>
          Consumes the Reset vector on IA
Serving as the root of trust in the system
Initial code that takes control of the system
May choose to authenticate the PEI Foundation 

Switch to 32-bit flat mode
Initialize the Boot strap processor BSP
Initialize PEI temporary memory NEM / CAR
Transfer control to PEI Core

SEC will have Platform specific functions
- AP waking stub
- Early microcode update
- Collect BIST (Built-in Self Test)
- Other charactistics of SEC   
  - Executed in place from flash
  - Written in assembly (16-bit & 32-bit)

-A Firmware Volume (FV) is a logical firmware device. The basic storage <br>
repository for data and/or code is the firmware volume. Each firmware volume is organized into a
file system. As such, the file is the base unit of storage for firmware

-Firmware File System <br>
A firmware file system (FFS) describes the organization of files and (optionally) free space within
the firmware volume. Each firmware file system has a unique GUID, which is used by the firmware
to associate a driver with a newly exposed firmware volume


---
### Go for it.
### Just add <span class="gold">PITCHME.md</span> ;)
<br>
[Click here to learn more @fa[external-link fa-pad-left]](https://github.com/gitpitch/gitpitch/wiki)
