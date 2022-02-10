# DDK_build_the_toolchain
Use the Crosstool-NG to generate the toolchain. <br/>

Host machine <br/>
uname -a <br/>
Linux ubuntu 5.13.0-28-generic #31~20.04.1-Ubuntu SMP Wed Jan 19 14:08:10 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux 
&nbsp;

Target machine <br/>
arm &nbsp;

# Download Crosstool-NG
git clone https://github.com/crosstool-ng/crosstool-ng crosstool-ng <br/>
cd crosstool-ng &nbsp;

# Create the Makefile
./configure --enable-local <br/>

## Issue
config.status: error: cannot find input file: `Makefile.in' <br/>
./autoreconf &nbsp;

## Issue
automake: error: cannot open < verbatim-data.mk: No such file or directory <br/>
./bootstrap &nbsp;

The bootstrap can create the verbatim-data.mk. &nbsp;

# Create the Crosstool-NG
make &nbsp;

# Install the Crosstool-NG
sudo make install &nbsp;

# Check the Crosstool-NG version
ct-ng --version <br/>
ct-ng --help &nbsp;

# Configure your toolchain
./ct-ng arm-cortex_a8-linux-gnueabi &nbsp;

  CONF  arm-cortex_a8-linux-gnueabi
#
# configuration written to .config
#

*********************************************************** &nbsp;

Initially reported by: Yann E. MORIN <br/>
URL: http://ymorin.is-a-geek.org/ <br/>

*********************************************************** &nbsp;

Now configured for "arm-cortex_a8-linux-gnueabi" &nbsp;

------------------------------------------------------------------------------ &nbsp;

# Build the toolchain
./ct-ng build &nbsp;
