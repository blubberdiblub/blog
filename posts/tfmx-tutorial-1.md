<!-- 
.. title: TFMX Tutorial 1
.. slug: tfmx-tutorial-1
.. date: 2016-11-17 19:43:42 UTC+01:00
.. tags: Amiga,TFMX,music,tutorial
.. category: Tutorial
.. link: 
.. description: How to set up a TFMX Sound Editor environment in FS-UAE.
.. type: text
-->

[TOC]

## Introduction

If we want to compose music like Chris Huelsbeck did back in his Amiga days,
we need to familiarize ourselves with his TFMX Sound System.

As the original ran on a Commodore Amiga computer and chances are we want to
use it on more modern hardware, we will need to set it up in an emulator.

This will work in all popular Amiga emulators such as WinUAE and FS-UAE and we
will see how to set it up in the latter one as this is the emulator I'm using
most often and is one that presents a more friendly configuration interface,
however, if you feel comfortable with WinUAE, you should have no problems
adapting the instructions for the former.

## Emulator Settings

We may want to adjust some FS-UAE settings, such as disabling the floppy drive
clicking emulation when there is no disk in the drive, as this might disturb
our audial experience. The sounds for when a disk is actually accessed provide
quite useful feedback, though, so we may want to leave those at the default:

[![Audio Settings][audio-settings-inline]][audio-settings-full]

We may prefer locking the aspect ratio instead of letting FS-UAE stretch and
squeeze the image as we resize the window:

[![Video Settings][video-settings-inline]][video-settings-full]

If we don't have it already, we will need to obtain and install FS-UAE. We can
get it from [the official FS-UAE website](https://fs-uae.net/download). For
this tutorial we will assume we have it already set up.

## Preparing Kickstart ROM's

The static part of the Amiga's operating system - called Kickstart - resides on
a ROM chip on the real hardware, which means we will have to provide a
Kickstart image file to the emulator. Unfortunately, the emulator's built-in
Kickstart as well as the AROS ROM images won't work with TFMX, so we will need
to obtain one of the copyrighted files. If we already own Cloanto's Amiga
Forever, we can copy it from that:

[![Amiga Forever Kickstarts][cloanto-kickstarts-inline]][cloanto-kickstarts-full]

We will need the `rom.key`, since the Cloanto ROM files come encrypted, as well
as `amiga-os-130.rom` for emulating an *Amiga 500* or `amiga-os-204.rom` for
emulating an *Amiga 500 +*. We should place them into the Kickstarts folder
that FS-UAE created for us:

[![FS-UAE Kickstarts Folder][kickstarts-folder-inline]][kickstarts-folder-full]

## Preparing Floppy Image

Of course we will also need to obtain an Amiga disk file (__ADF__ for short)
containing TFMX, which I cannot offer for download here for obvious reasons.
We ought to be able to find one on any of the usual Amiga scene websites. We
should place this into the `Floppies` folder FS-UAE created for us:

[![FS-UAE Floppies Folder][floppies-folder-inline]][floppies-folder-full]

We should ask FS-UAE to update its file database to make sure it keeps track
of what files are available:

[![FS-UAE Update File Database Menu Item][file-database-menu-inline]][file-database-menu-full]

The _Scan_ button updates FS-UAE's database and depending on which Kickstarts
we dropped into the folder, it shows us which Amiga systems it will emulate:

[![FS-UAE Update File Database Dialog][file-database-dialog-inline]][file-database-dialog-full]

## Creating a Configuration

Now we are ready to create a configuration for TFMX. We will start at the home
tab, which is the most important one. There are several items here we need to
pay attention to:

* _NTSC_ needs to be unchecked. TFMX is designed for PAL systems. Usually we
  shouldn't need to change this, as it is disabled by default.
* Accuracy should be left at _High_ so TFMX doesn't surprise us with timing
  and graphics related incompatibilities.
* We choose either *A500* or *A500+* as Amiga Model.
* We select the disk image we downloaded earlier as emulated floppy disk.
* Whereas we don't need to emulate a joystick when being productive with TFMX,
  we still need to make sure the cursor keys are not selected to be mapped to
  joystick directions, as that would make them unavailable as standard cursor
  keys inside the editor. Either _No Host Device_ or an actual controller will
  work for us here.

[![FS-UAE Main Configuration][main-config-inline]][main-config-full]

We most likely want our creations to be available directly as files on our host
system, so we also need to set up a directory to be made available as hard
drive in the emulator:

[![FS-UAE Hard Drive][hard-drive-inline]][hard-drive-full]

We can designate a directory anywhere on our system, but for simplicity's sake
we'll use the _Hard Drives_ folder FS-UAE set up for us. We name our new folder
in there _TFMX_ or anything else we like:

[![FS-UAE TFMX Folder][tfmx-folder-inline]][tfmx-folder-full]

Inside the _TFMX_ folder, we create the subfolders _samples_ and _songs_, which
will make our life easier as TFMX will look for those names later:

[![FS-UAE TFMX Subfolders][tfmx-subfolders-inline]][tfmx-subfolders-full]

We make sure the TFMX folder appeared in the Hard Drive input field after
confirming the folder selection dialog.

On the ROM & RAM tab, we can crank up the emulated amount of RAM. Only the left
half will work for this system. _Chip RAM_ is most important, as the sound
samples can only be played from there and those will generally take up the most
space, but it doesn't hurt increasing the _Ranger ("Slow") RAM_ and _Fast RAM_
as well:

[![FS-UAE RAM][ram-inline]][ram-full]

If we like, we can set the floppy drive speed to _Turbo_ in order to reduce the
load and save times somewhat, but if we prefer more pleasing floppy activity
sound emulation, we can also leave it at the default.

To finish setting up, we give our configuration a name and save it into the
list. After that we're ready to _start_ our virtual Amiga:

[![FS-UAE Save Configuration][save-config-inline]][save-config-full]

## Starting TFMX

After some potential intro, we're presented with a menu of choices. As we
should have configured a lot of RAM, we are free to start the generous 16 color
version of the editor with *F3*:

[![TFMX Menu][tfmx-menu-inline]][tfmx-menu-full]

We are directly thrown into the track editor, but we might want to change one
setting first, accessible by clicking on one of the title buttons:

[![TFMX Initial Screen][tfmx-initial-inline]][tfmx-initial-full]

Our enjoyment of the music will be disturbed by the metronome, which will click
away during playback, so we may switch it off here:

[![TFMX Metronome][tfmx-metronome-inline]][tfmx-metronome-full]

Let's try loading up a song. We switch to the _load song_ screen and double
click one of the example songs on the disk:

[![TFMX Load Song][tfmx-load-song-inline]][tfmx-load-song-full]

## Getting out of AmigaOS Requester Hell

As this is the first time when we might accidentally make a mistake that could
get us stuck or at least confused if we're not accustomed to AmigaOS, we will
now exercise getting out of that situation correctly.

The buttons labelled _DF0_, _DF1_, _DF2_, _DF3_, _DH0_ and _DH1_ let us switch
to a different drive, where `DFx` designates a possible floppy drives and `DHx`
designates a possible hard drive. And if we happen to click on a drive that
doesn't exist or which doesn't contain a volume, the screen will suddenly
switch back to where the menu was earlier.

But that doesn't mean the TFMX editor has exited. It's still running in the
background and we shouldn't try to start a second instance of the program.

The first thing we should do in that situation is cancelling the requesters
that appear, which we may have to repeat several times before the OS gives up
bugging us:

[![AmigaOS Volume Requester][volume-requester-inline]][volume-requester-full]

Then we will have to move the AmigaDOS window down a bit to reveal the controls
that allow us to return to the editor:

[![AmigaOS Move AmigaDOS Window][move-window-inline]][move-window-full]

The buttons we need are located at the top right and the lefthand one of them
puts the Workbench screen to the background. (In case we used an *Amiga 500+*
with Kickstart 2.04, there'll be only one button).

Alternatively, if we had a real Amiga keyboard, we could press the shortcut
*Amiga* + *M* to shuffle the Workbench screen to the background. The *Amiga*
key is mapped to the *Windows* or *Super* key by default, so on our emulator
the combination should be *Windows* + *M* or *Super* + *M*, respectively.

[![AmigaOS Shuffle Screens][shuffle-screens-inline]][shuffle-screens-full]

## Fooling Around

After this little detour, we can enjoy the song by pressing the _Play_ button:

[![TFMX Play Song][tfmx-play-song-inline]][tfmx-play-song-full]

We can also play around with the editor to our heart's content and if we like
what we created, we should save our song to the folder we set up earlier.

On the emulated Amiga, this is accessible on the _DH0_ drive, so after going
to the _Save Song_ screen, we click the _DH0_ button before we store the song
by pressing the _Enter_ key (after changing the name, if desired):

[![TFMX Save Song][tfmx-save-song-inline]][tfmx-save-song-full]

We can leave TFMX by clicking the _ESC_ button and then confirming the request
at the top with the right mouse button:

## Quitting TFMX

[![TFMX Exit][tfmx-exit-inline]][tfmx-exit-full]

## Conclusion and Upcoming

Today we practised setting up our emulator to run the TFMX Sound System and
made our first steps to familiarize ourselves with the environment.

In the next tutorial we will load a sampled sound and will set up a macro in
order to actually make use of it.


[audio-settings-full]: /images/tfmx-tutorial-1/01-fs-uae-settings-audio.png
[audio-settings-inline]: /images/tfmx-tutorial-1/01-fs-uae-settings-audio.thumbnail.png

[video-settings-full]: /images/tfmx-tutorial-1/02-fs-uae-settings-video.png
[video-settings-inline]: /images/tfmx-tutorial-1/02-fs-uae-settings-video.thumbnail.png

[cloanto-kickstarts-full]: /images/tfmx-tutorial-1/03-amiga-forever-kickstarts.png
[cloanto-kickstarts-inline]: /images/tfmx-tutorial-1/03-amiga-forever-kickstarts.thumbnail.png

[kickstarts-folder-full]: /images/tfmx-tutorial-1/04-fs-uae-kickstarts.png
[kickstarts-folder-inline]: /images/tfmx-tutorial-1/04-fs-uae-kickstarts.thumbnail.png

[floppies-folder-full]: /images/tfmx-tutorial-1/05-fs-uae-floppies.png
[floppies-folder-inline]: /images/tfmx-tutorial-1/05-fs-uae-floppies.thumbnail.png

[file-database-menu-full]: /images/tfmx-tutorial-1/06-fs-uae-update-file-database.png
[file-database-menu-inline]: /images/tfmx-tutorial-1/06-fs-uae-update-file-database.thumbnail.png

[file-database-dialog-full]: /images/tfmx-tutorial-1/07-fs-uae-update-file-database.png
[file-database-dialog-inline]: /images/tfmx-tutorial-1/07-fs-uae-update-file-database.thumbnail.png

[main-config-full]: /images/tfmx-tutorial-1/08-fs-uae-floppy-image.png
[main-config-inline]: /images/tfmx-tutorial-1/08-fs-uae-floppy-image.thumbnail.png

[hard-drive-full]: /images/tfmx-tutorial-1/09-fs-uae-hard-drive.png
[hard-drive-inline]: /images/tfmx-tutorial-1/09-fs-uae-hard-drive.thumbnail.png

[tfmx-folder-full]: /images/tfmx-tutorial-1/10-fs-uae-directory-tfmx.png
[tfmx-folder-inline]: /images/tfmx-tutorial-1/10-fs-uae-directory-tfmx.thumbnail.png

[tfmx-subfolders-full]: /images/tfmx-tutorial-1/11-fs-uae-directories-samples-songs.png
[tfmx-subfolders-inline]: /images/tfmx-tutorial-1/11-fs-uae-directories-samples-songs.thumbnail.png

[ram-full]: /images/tfmx-tutorial-1/12-fs-uae-ram.png
[ram-inline]: /images/tfmx-tutorial-1/12-fs-uae-ram.thumbnail.png

[save-config-full]: /images/tfmx-tutorial-1/13-fs-uae-save-config.png
[save-config-inline]: /images/tfmx-tutorial-1/13-fs-uae-save-config.thumbnail.png

[tfmx-menu-full]: /images/tfmx-tutorial-1/14-tfmx-menu.png
[tfmx-menu-inline]: /images/tfmx-tutorial-1/14-tfmx-menu.thumbnail.png

[tfmx-initial-full]: /images/tfmx-tutorial-1/15-tfmx-initial.png
[tfmx-initial-inline]: /images/tfmx-tutorial-1/15-tfmx-initial.thumbnail.png

[tfmx-metronome-full]: /images/tfmx-tutorial-1/16-tfmx-metronome.png
[tfmx-metronome-inline]: /images/tfmx-tutorial-1/16-tfmx-metronome.thumbnail.png

[tfmx-load-song-full]: /images/tfmx-tutorial-1/17-tfmx-load-song.png
[tfmx-load-song-inline]: /images/tfmx-tutorial-1/17-tfmx-load-song.thumbnail.png

[volume-requester-full]: /images/tfmx-tutorial-1/19-tfmx-wrong-drive.png
[volume-requester-inline]: /images/tfmx-tutorial-1/19-tfmx-wrong-drive.thumbnail.png

[move-window-full]: /images/tfmx-tutorial-1/20-tfmx-move-amigados-window.png
[move-window-inline]: /images/tfmx-tutorial-1/20-tfmx-move-amigados-window.thumbnail.png

[shuffle-screens-full]: /images/tfmx-tutorial-1/21-tfmx-shuffle-screens.png
[shuffle-screens-inline]: /images/tfmx-tutorial-1/21-tfmx-shuffle-screens.thumbnail.png

[tfmx-play-song-full]: /images/tfmx-tutorial-1/18-tfmx-play-song.png
[tfmx-play-song-inline]: /images/tfmx-tutorial-1/18-tfmx-play-song.thumbnail.png

[tfmx-save-song-full]: /images/tfmx-tutorial-1/22-tfmx-save-song.png
[tfmx-save-song-inline]: /images/tfmx-tutorial-1/22-tfmx-save-song.thumbnail.png

[tfmx-exit-full]: /images/tfmx-tutorial-1/23-tfmx-exit.png
[tfmx-exit-inline]: /images/tfmx-tutorial-1/23-tfmx-exit.thumbnail.png
