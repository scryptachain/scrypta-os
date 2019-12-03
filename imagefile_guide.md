# Complete guide for Raspberry PI4 installation with file image.

The image file for your Raspberry PI4 is based on Raspbian Debian Buster with all libraries already installed and a working wallet.
You can burn the file image on your SD card following our installation guide.


<p>This resource explains how to install a Raspberry Pi operating system image on an SD card. <br />You will need another computer with an SD card reader to install the image.</p>
<h2>Download the image and write it to your SD card</h2>
<p>Scrypta official image file is available to download from the <a href="https://www.scryptachain.org/wallet/scryptaOS_rasp_1.1.0.img/">Scrypta official server</a>.</p>
<p>You will need to use an image writing tool to install the image you have downloaded on your SD card.</p>
<p><strong>balenaEtcher</strong>&nbsp;is a graphical SD card writing tool that works on Mac OS, Linux and Windows, and is the easiest option for most users. balenaEtcher also supports writing images directly from the zip file, without any unzipping required. To write your image with balenaEtcher:</p>
<ul>
<li>Download the latest version of&nbsp;<a href="https://www.balena.io/etcher/">balenaEtcher</a>&nbsp;and install it.</li>
<li>Connect an SD card reader with the SD card inside.</li>
<li>Open balenaEtcher and select from your hard drive the Scrypta&nbsp;<code>.img</code>&nbsp;file you wish to write to the SD card.</li>
<li>Select the SD card you wish to write your image to.</li>
<li>Review your selections and click 'Flash!' to begin writing data to the SD card.</li>
</ul>
<p>Wait until the process is complete, then insert the SD Card to the Raspberry PI4.</p>
<p>Please note: for users security reasons, the wallet installed on your system come without <code>wallet.dat</code> file to ensure users that nobody have private keys of your wallet. The <code>wallet.dat</code> file wil be generated when you launch the wallet fo<p><strong>Please note:</strong> for users security reasons, the wallet installed on your system come without <code>wallet.dat</code> file to ensure users that nobody have private keys of your wallet. <br />The <code>wallet.dat</code> file wil be generated when you launch the wallet for the first time.</p>
