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

<p align="center"><span style="color:gray; font-size:0.5em"> <b>UEFI  and Platform Initialziation (PI) Boot Execution Flow</b> </span>
Note:
The next set of slides will detail the phases of the boot execution flow for UEFI
    
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
@title[UEFI Boot Flow PEI]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>PEI</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg4_1.png =10x)


Note:
PEI Function <Br>
- PEI Primary goals:
  -	Discover boot mode (Normal, S3, Recovery)
  - Discover and initialize some RAM that won’t be reconfigured
  -	Discover location of FV(s) containing DXE Core & Architecture Protocols and Launch DXE core

- PEI Phases – 
   - Pre – memory Init
   - Memory reference code (MRC)
   - Post Memory Init

Components: 
- Binaries: PEI Core and PEI Modules (PEIMs)
PEIMs are modules scheduled by the PEI core in the early phase of platform initialization. PEIMs are typically executed in place before system memory is available. 
- On IA running in No Eviction mode (NEM) aka.  Cache as RAM

Interfaces: Methods of Inter-PEIM communication
Core set of services (PeiServices), PEIM to PEIM Interfaces (PPIs), and simple Notifies (no timer in PEI)




---
@title[UEFI Boot Flow PEI-Hobs]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>Hobs</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg5.png =10x)


Note:
PEI - Hobs <Br>
Transition to DXE :
- HOBS  – a series of data structures in memory, created during PEI, that describe platform features, configuration, or data. HOBs are produced during PEI, and read-only during DXE (consumer). 

- **DXE IPL** 
- No hard coded addresses allowed
- Find Largest Physical Memory HOB
  - Ideally this should be near Top Of Memory (TOM)
  - Allocate DXE Stack from Top of Memory
- Build HOB that describes DXE Stack
- Search FVs from HOB List for DXE Core
- Load DXE Core into Memory (PE/COFF)
- Build HOB that describes DXE Core
- Switch Stacks and Handoff to DXE Core

---
@title[UEFI Boot Flow DXE]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>DXE</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg5_1.png =10x)


Note:
DXE <Br>
---
@title[UEFI Boot Flow DXE]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>DXE</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg6.png =10x)


Note:
DXE - EFI System Table<Br>   

+++
@title[UEFI Boot Flow EFI System Table]
#### <p align="center"><span class="gold"  text-align: top >UEFI System Table </span>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg7.png =10x)
Note:
DXE - EFI System Table<Br>   
Created in DXE and is the pointer to everything in the system

---
@title[UEFI Boot Flow DXE- UEFI Drivers]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>DXE</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg8.png =10x)


Note:
DXE - UEFI Drivers<Br>

---
@title[UEFI Boot Flow BDS]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>BDS</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg9.png =10x)


Note:
BDS<Br>

+++
@title[UEFI Boot Flow Device Path]
#### <p align="center"><span class="gold"  text-align: top >UEFI Device Path and Global Variables</span>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg10_1.png =10x)


Note:
Device Path and Global Variables<Br>

---
@title[UEFI Boot Flow HII]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>HII</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg11.png =10x)


Note:
HII<Br>
    
+++
@title[UEFI Boot Flow HII- Simple]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>HII</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg12.png =10x)
Note:
HII<Br>
    Simple
+++
@title[UEFI Boot Flow HII- Complex]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>HII</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg13.png =10x)

Note:
HII<Br>
    Complex
---
@title[UEFI Boot Flow Shell]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>TSL</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg14.png =10x)


Note:
UEFI Shell<Br>
---
@title[UEFI Boot Flow Boot Loader]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">-&nbsp;<b>Boot Loader</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg15.png =10x)


Note:
Boot Loader<Br>

+++                
@title[UEFI Boot Flow Boot UEFI OS]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">-&nbsp;<b>Boot UEFI OS</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg16.png =10x)


Note:
Boot UEFI OS<Br>

---
@title[UEFI Boot Legacy]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">-&nbsp;<b>Boot Legacy</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg17.png =10x)


Note:
Legacy boot with CSM<Br>

+++
@title[UEFI Boot Legacy no UEFI]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;-&nbsp;<b>Boot Legacy</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg18.png =10x)


Note:
Legacy boot with CSM<Br>

---
@title[Intel FSP Section]
#### <p align="center"><span class="gold"  text-align: top >The Intel® Firmware Support Package <BR> (Intel® FSP)
</span>
Note:
Section on Intel FSP
---
@title[Intel FSP Description]
##### <span class="gold"  text-align: top >Intel® FSP  -  Components </span>
- CPU, memory controller, and chipset initialization functions as a binary package
- Provides silicon initialization ingredients
- Plugs into existing firmware frameworks
- Integration guide, includes API documentation

<p align="left" style="margin-top: -3px; margin-bottom: -3px"><span style="color:white; font-size:0.5em"> 
<br>
<BR>
Intel FSP is currently available for the many Intel hardware-producing divisions &nbsp;&nbsp;&nbsp;
See: <a href="https://firmware.intel.com/learn/fsp/about-intel-fsp"> About Intel FSP</a> <br>
White Paper Example: <a href="https://github.com/mangguo321/Braswell/blob/master/Documents/Open_Braswell_Platform_Designing_Porting_Guide.pdf">
Open Braswell - Design and Porting Guide</a></span></p>

---
@title[Intel FSP Diagram-1]
#### <p align="center"><span class="gold"  text-align: top >Intel® FSP to Open Source EDK II </span>
    
![Intel-FSP](/assets/images/bgpages/bg21.png =10x)


Note:
Intel FSP 1<Br>
+++
@title[Intel FSP Diagram-2]
#### <p align="center"><span class="gold"  text-align: top >Intel® FSP to Open Source EDK II </span>
    
![Intel-FSP](/assets/images/bgpages/bg22.png =10x)


Note:
Intel FSP 2<Br>    
+++
@title[Intel FSP Diagram-3]

<p align="center" style="margin-top: -3px; margin-bottom: -3px"><span style="color:white; font-size:0.75em"> 
Intel®  FSP "Produced" to <br> "Consuming" Intel® Architecture Firmware </span>
    
![Intel-FSP](/assets/images/bgpages/bg23_1.png =10x)


Note:
Applying “Produced” Intel® Firmware Support Package (FSP) to “Consuming” IA firmware <Br>  

---
@title[Intel FSP from UEFI Boot Flow]
#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>FSP</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg26.png =10x)


Note:
Platform Initialization (PI) & UEFI w/ EDK <Br>
- Intel FSP boot flow    

+++
@title[Intel FSP from UEFI Boot Flow 2]

#### <p align="center"><span class="gold"  text-align: top >UEFI - PI & EDK II Boot Flow </span><span style="color:white;">&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;<b>FSP</b> </span></p>

![UEFI Boot Execution Flow](/assets/images/bgpages/bg25.png =10x)


Note:
Platform Initialization (PI) & UEFI w/ EDK <Br>
- Intel FSP boot flow    

---
@title[Intel FSP Producer]
##### <span class="gold"  text-align: top >Intel® FSP  - Producer </span>

- Examples of binary instances on http://www.intel.com/fsp with integration guides 
- This includes hardware initialization code that is EDK II based PEI Modules (PEIM’s)
- Modules are encapsulated as a UEFI PI firmware volume w/ extra header
- Configure w/Vital Product Data (VPD)-style Platform Configuration Data (PCD) externalized from the modules
- Resultant output state reported via UEFI Platform Initialization (PI) Hand Off Block (HOB)
- <a href="http://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/fsp-architecture-spec-v2.pdf"> Intel® Firmware Support Package (Intel® FSP) External Architecture Specification (EAS) v2.0 </a>
- Resource: https://firmware.intel.com/blog/open-source-platforms-edkii-using-intel-fsp 
---
@title[Intel FSP Source]
##### <span class="gold"  text-align: top >Source for Intel® FSP  Producer Code</span>
- CPU and chipset-specific code for PEIM’s inside of the Intel FSP can be open or closed, added to…
- PEI core and infrastructure code at <a href="https://github.com/tianocore/edk2"> tianocore.org/edk2 </a>
  - <a href="https://github.com/tianocore/edk2/tree/master/MdePkg"> /MdePkg </a>
  - <a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg"> /MdeModulePkg </a>
- And the code to create the Intel FSP interfaces can be found at 
   - <a href="https://github.com/tianocore/edk2/tree/master/IntelFsp2Pkg"> /IntelFsp2Pkg </a>


---  
@title[Whats New in UEFI Section]    
#### <p align="center"><span class="gold"  text-align: top >What's new in the UEFI Specifications </span>
    </p>
---  
@title[UEFI Spec pic]    
#### <p align="center"><span class="gold"  text-align: top >Latest Specifications </span>
    </p>
![UEFI Spec Icons](/assets/images/bgpages/bg29.png =10x) 

Notes:
- UEFI Specifications v2.7A (9/2017)
- ACPI Specification v6.2 (5/2017)
- UEFI Shell Specification v2.2 (1/2016)
- PI Packaging Specification v1.1 (1/2016)
- UEFI PI Specification v1.6 (5/2017)




---


### Go for it.
### Just add <span class="gold">PITCHME.md</span> ;)
<br>
[Click here to learn more @fa[external-link fa-pad-left]](https://github.com/gitpitch/gitpitch/wiki)
