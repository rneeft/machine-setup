# Ubuntu machine

## install dotnet

```bash
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
``` 
```bash
chmod +x ./dotnet-install.sh
``` 
```bash
./dotnet-install.sh --version latest
``` 
```bash
dotnet workload install aspire
``` 
```bash
dotnet workload install maui-android
``` 

```bash
export DOTNET_ROOT=$HOME/.dotnet
```
```bash
export PATH=$PATH:$DOTNET_ROOT:$DOTNET_ROOT/tools
```
```bash
dotnet --info
```

Install visualstudio code from here: https://code.visualstudio.com/

## Install 
