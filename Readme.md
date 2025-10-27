# RedButton Browser - part of RedButton MHEG Engine

This is a fork of rb-browser by Simon Kilvington (https://sourceforge.net/u/skilvington/profile/), with updated ffmpeg code by Conor Keegan (https://github.com/kronoc). It emulates the MHEG-5 functions of a basic DVB receiver circa 2003, up to the original profile spec only (i.e. no Internet extensions etc).

I have made minor changes to allow the manual selection of the service ID. While this was possible in the original code, it required a specific directory layout. The UK Freeview network ID of 9018 is also now used by default.

It has been tested on a typical Ubuntu 22.04 LTS system.

## Dependencies

```sudo apt install libfreetype6-dev libavformat-dev libxrender-dev libxft-dev libxt-dev libxext-dev ffmpeg-dev libavcodec-dev libavcodec-dev libavformat-dev libavutil-dev libswscale-dev libasound2-dev libbz2-dev xsltproc```

To build simply run `make` (presuming you have the usual build tools for your platform installed)

## Usage

`rb-browser [-v] [-f] [-d] [-o <video_output_method>] [-k <keymap_config_file>] [-t <timeout>] [-n <network_id>] [-s <service_id>] [-r] [<service_gateway>]`

Display the MHEG apps downloaded with rb-download (or similar). For example, to view a previously captured MHEG-5 carousel:

`rb-browser -s 12345 path/to/carousel/`

### Default Keys

**Cursor Keys:** Up/Down/Left/Right

**0-9:** 0-9

**r:** Red

**g:** Green

**b:** Blue

**y:** Yellow

**Return:** OK/Select

**Escape:** Cancel

**t:** Text

**e:** EPG (NZ Profile only)

## Notes

The default font for the UK MHEG Profile is Tiresias Screenfont which was developed with the RNIB to be readable on TV screens. You can download this font as part of the DigiTV iTuner package from Nebula Electronics. Extract the file called tt7268m_802.ttf and add it to your X Windows fonts. The easiest way is to install DigiTV iTuner on a Windows PC and then copy the C:\Windows\Fonts\tt7268m_802.ttf file onto your Linux PC. To install new X fonts in KDE, open the Control Centre application, go to the System Administration section and select Font Installer.

If the Tiresias Screenfont is not available, rb-browser first tries to use the FreeSans font instead. If this is also not available, rb-browser uses whatever scalable font Xft returns for "sans". Note that these fonts will have different metrics and so may not fit into the spaces in the MHEG apps designed for Tiresias.
