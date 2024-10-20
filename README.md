# 🐧 Fruity-Linux

In this documentation, we will see how to install, configure and use the last version of FL Studio on Linux.

## 📋 Prerequisites

- A computer running Linux
- A FL Studio license

## 📥 Installation

### 🍷 Install Wine

First, you need to install Wine. Wine is a compatibility layer that allows you to run Windows applications on Linux.

Download and add the repository key:

```bash
sudo mkdir -pm755 /etc/apt/keyrings
sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key
```

Since I use Ubuntu, I will add the repository for Ubuntu 22.04:

```bash
sudo wget -NP /etc/apt/sources.list.d/ https://dl.winehq.org/wine-builds/ubuntu/dists/jammy/winehq-jammy.sources
```

Visit this [page](https://wiki.winehq.org/Ubuntu) to get the repository for your Ubuntu version.
For other distributions, visit this [page](https://wiki.winehq.org/Download).

Update the package list and install Wine:

```bash
sudo apt update
sudo apt install --install-recommends winehq-stable
```

### 📥 Install FL Studio

Download the latest version of FL Studio from the [official website](https://www.image-line.com/fl-studio-download/). Download the Windows version. Follow the instructions to install it, with ASIO4ALL and FL Studio ASIO.

## 🛠️ Configuration

### 🍷 Configure Wine

Open Wine configuration:

```bash
winecfg
```

Click on "Add application" and select the FL Studio executable (usually in Program Files/Image-Line/FL Studio {version}/FL64.exe). Also, add the scaled version. Once added, select the executable and change the Windows version to Windows 7, again do it for the scaled version. Click on "Apply" and "OK".

### 🔊 Configure the audio settings

If needed, you can configure the audio settings in FL Studio. Run FL Studio and go to Options > Audio settings, select FL Studio ASIO as the audio device and click on "Show ASIO panel". In the ASIO panel, select your audio interface and click on "Apply".

## ✨ Customization

>_The following steps are optional_

### 📦 Add sample packs

Open your file manager and go the home directory. Press `Ctrl+H` to show hidden files and folders. Go to `.wine/drive_c/Program Files/Image-Line/FL Studio {version}/Data/Patches/Packs` and copy your sample packs in this folder.

### 🎹 Add VST plugins

In the FL Studio installation directory, go to `Plugins/VST` (create the `VST` directory if non-existant) and copy your VST plugins in this folder. If you need to install exe plugins, you can do it with Wine. Right-click on the exe file and select "Open with Wine Windows Program Loader". Some plugins may not work with Wine.

### 🎨 Add custom themes

In your `Documents`, go to `Image-Line/FL-Studio/Settings/Themes` and copy your custom theme in this folder. Your can find custom themes on [this page](https://forum.image-line.com/viewforum.php?f=2003) or [this page](https://stickz.co/blog/top-10-best-fl-studio-21-themes/). My custom theme is available in the `theme` folder.

Now you can select your custom theme in FL Studio by going to Options > Theme settings.

## 🚀 Usage

Run FL Studio and start creating music!
