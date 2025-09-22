# crispy-funicular

## Dependencies
```
dotnet add package Telegram.Bot
dotnet add package DSharpPlus
dotnet add package DSharpPlus.VoiceNext
dotnet add package Matrix.NET.Core
dotnet add package NAudio
dotnet add package FFMpegCore
```
### Ubuntu-Debian
```

sudo apt-get update
sudo apt-get install -y \
    build-essential \
    cmake \
    pkg-config \
    libssl-dev \
    libasio-dev \
    ffmpeg \
    python3 \
    python3-pip
```

```
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install -y dotnet-sdk-6.0
```
### For Windows
```
git clone https://github.com/Microsoft/vcpkg.git
cd vcpkg
.\bootstrap-vcpkg.bat
.\vcpkg install cpprestsdk opus portaudio
```
### MacOS
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install cmake cpprestsdk opus flac portaudio ffmpeg
brew install --cask dotnet-sdk
```
### Dockerfile

```
FROM mcr.microsoft.com/dotnet/sdk:6.0

WORKDIR /app
COPY *.csproj ./
RUN dotnet restore

COPY . ./
RUN dotnet publish -c Release -o out

CMD ["dotnet", "out/bot.dll"]
```
