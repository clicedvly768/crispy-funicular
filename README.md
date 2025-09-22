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
