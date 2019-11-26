this is a diary of me reverse engineering fate grand order. this assumes
you have read my love live all stars diary https://github.com/Francesco149/reversing-sifas
and does not explain things already explained there. as usual this is uncut
and observations might be corrected later

first things I do is look for strings that look like url's to find the
config class that potentially holds other things like keys and stuff

this looks promising:

```c
void ManagerConfig$$.cctor(void)

{
  int iVar1;
  int iVar2;
  
  if (DAT_027ed923 == '\0') {
    FUN_003479b0(0x5dc4);
    DAT_027ed923 = '\x01';
  }
  **(undefined4 **)(Class$ManagerConfig + 0x5c) = "2.4.2";
  iVar1 = Class$ManagerConfig;
  *(undefined4 *)(*(int *)(Class$ManagerConfig + 0x5c) + 4) =
       "f8a11e47a2423c919c09d0a22dcf0155847ca1943e09045b3035f6e318845d40";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 8) = "20191115_14:26";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0xc) = "Fgo_20150511_1";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x10) = "Fgo_20180629_1";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x14) = 0x42b40000;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x18) = 0x43160000;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x1c) = 0x3f800000;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x20) = 0x40000000;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x24) = 0x40000000;
  iVar2 = *(int *)(iVar1 + 0x5c);
  *(undefined4 *)(iVar2 + 0x28) = 0xe10;
  *(undefined4 *)(iVar2 + 0x2c) = 0;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x30) = 0x41200000;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x34) = 3;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x38) = 0x400;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x3c) = 0x240;
  iVar2 = *(int *)(iVar1 + 0x5c);
  *(undefined4 *)(iVar2 + 0x40) = 0x3200000;
  *(undefined4 *)(iVar2 + 0x44) = 0;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x48) = 0x3ba3d70a;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x4c) = "com.aniplex.fategrandorder";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x50) = "1015521325";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x54) = "Android";
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x58) = 1;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x5c) = "game.fate-go.jp";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x60) = "https://cdn.data.fate-go.jp/AssetStorages";
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 100) = "webview.fate-go.jp";
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x68) = 0;
  if (((*(byte *)(Class$string + 0xbf) & 2) != 0) && (*(int *)(Class$string + 0x70) == 0)) {
    FUN_0035803c();
  }
  iVar2 = Class$ManagerConfig;
  iVar1 = Class$string;
  *(undefined4 *)(*(int *)(Class$ManagerConfig + 0x5c) + 0x6c) =
       **(undefined4 **)(Class$string + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x70) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x74) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0x78) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x7c) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x80) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x84) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0x88) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x8c) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x90) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x94) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0x98) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x9c) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xa0) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xa4) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0xa8) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xac) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xb0) = **(undefined4 **)(iVar1 + 0x5c);
  iVar2 = Class$ManagerConfig;
  iVar1 = Class$string;
  *(undefined4 *)(*(int *)(Class$ManagerConfig + 0x5c) + 0xb4) =
       **(undefined4 **)(Class$string + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0xb8) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xbc) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xc0) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xc4) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 200) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xcc) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xd0) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xd4) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0xd8) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xdc) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xe0) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xe4) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0xe8) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xec) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0xf0) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xf4) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0xf8) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0xfc) = 0;
  iVar2 = Class$ManagerConfig;
  iVar1 = Class$string;
  *(undefined4 *)(*(int *)(Class$ManagerConfig + 0x5c) + 0x100) =
       **(undefined4 **)(Class$string + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x104) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x108) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x10c) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0x110) = 0;
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0x111) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x114) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x118) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 0x11c) = 0;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x120) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x124) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x128) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined *)(*(int *)(iVar2 + 0x5c) + 300) = 1;
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x130) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x134) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x138) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x13c) = **(undefined4 **)(iVar1 + 0x5c);
  *(undefined4 *)(*(int *)(iVar2 + 0x5c) + 0x140) = **(undefined4 **)(iVar1 + 0x5c);
  iVar1 = Class$ManagerConfig;
  *(undefined4 *)(*(int *)(Class$ManagerConfig + 0x5c) + 0x144) =
       **(undefined4 **)(Class$string + 0x5c);
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x148) = 1;
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x149) = 1;
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x14a) = 0;
  *(undefined4 *)(*(int *)(iVar1 + 0x5c) + 0x14c) = "RELEASE";
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x150) = *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x148);
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x151) = 0;
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x152) = 0;
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x153) = 0;
  *(undefined *)(*(int *)(iVar1 + 0x5c) + 0x154) = 0;
  return;
}
```

just need to clean it up by mapping the struct

those hex values are likely floats and you can easily confirm by setting
them to float and verifying that they are meaningful numbers

this is what i mapped so far, don't really care about the rest for now

```c
  Class$ManagerConfig->instance->version = "2.4.2";
  paVar2 = Class$ManagerConfig;
  Class$ManagerConfig->instance->someHash =
       "f8a11e47a2423c919c09d0a22dcf0155847ca1943e09045b3035f6e318845d40";
  paVar2->instance->buildDateTime = "20191115_14:26";
  paVar2->instance->buildNumber1 = "Fgo_20150511_1";
  paVar2->instance->buildNumber2 = "Fgo_20180629_1";
  paVar2->instance->float_0x14 = 90.00000000;
  paVar2->instance->float_0x18 = 150.00000000;
  paVar2->instance->float_0x1c = 1.00000000;
  paVar2->instance->float_0x20 = 2.00000000;
  paVar2->instance->float_0x24 = 2.00000000;
  pMVar3 = paVar2->instance;
  pMVar3->field_0x28 = 0xe10;
  pMVar3->field_0x2c = 0;
  paVar2->instance->float_0x30 = 10.00000000;
  paVar2->instance->field_0x34 = 3;
  paVar2->instance->field_0x38 = 0x400;
  paVar2->instance->field_0x3c = 0x240;
  pMVar3 = paVar2->instance;
  pMVar3->field_0x40 = 0x3200000;
  pMVar3->field_0x44 = 0;
  paVar2->instance->float_0x48 = 0.00500000;
  paVar2->instance->androidPackageName = "com.aniplex.fategrandorder";
  paVar2->instance->applePackageName = "1015521325";
  paVar2->instance->platform = "Android";
  *(undefined *)&paVar2->instance->field_0x58 = 1;
  paVar2->instance->endpointHost = "game.fate-go.jp";
  paVar2->instance->assetsEndpoint = "https://cdn.data.fate-go.jp/AssetStorages";
  paVar2->instance->webviewHost = "webview.fate-go.jp";
  *(undefined *)&paVar2->instance->field_0x68 = 0;
```

so i wonder what that hash is. let's search for references to it

looks like it's verCode:

```c
  RequestBase$$addField(param_1,"lastAccessTime",(int)((ulonglong)uVar3 >> 0x20),(int)uVar3,0);
  verCode = Class$ManagerConfig->instance->someHash;
  if (param_1 == 0) {
    FUN_003733b8(0);
  }
  RequestBase$$addField(param_1,"verCode",verCode,0);
```

lots of other interesting fields in here:

```c
void NetworkManager$$SetBaseField(int param_1)

{
  int iVar1;
  undefined4 uVar2;
  char *tmp1;
  undefined8 uVar3;
  
  if (DAT_027ee62e == '\0') {
    FUN_003479b0(0x65de);
    DAT_027ee62e = '\x01';
  }
  if (((*(byte *)(Class$NetworkManager + 0xbf) & 2) != 0) &&
     (*(int *)(Class$NetworkManager + 0x70) == 0)) {
    FUN_0035803c();
  }
  iVar1 = *(int *)(*(int *)(Class$NetworkManager + 0x5c) + 0x48);
  if (iVar1 != 0) {
    if (((*(byte *)(Class$NetworkManager + 0xbf) & 2) != 0) &&
       (*(int *)(Class$NetworkManager + 0x70) == 0)) {
      FUN_0035803c();
      iVar1 = *(int *)(*(int *)(Class$NetworkManager + 0x5c) + 0x48);
    }
    if (param_1 == 0) {
      FUN_003733b8(0);
    }
    RequestBase$$addField(param_1,"userId",iVar1,0);
    uVar2 = *(undefined4 *)(*(int *)(Class$NetworkManager + 0x5c) + 0x4c);
    if (param_1 == 0) {
      FUN_003733b8(0);
    }
    RequestBase$$addField(param_1,"authKey",uVar2,0);
  }
  if (((*(byte *)((int)&Class$ManagerConfig[1].instance + 3) & 2) != 0) &&
     (*(int *)&Class$ManagerConfig[1].field_0x10 == 0)) {
    FUN_0035803c();
  }
  tmp1 = Class$ManagerConfig->instance->appVer;
  if (param_1 == 0) {
    FUN_003733b8(0);
  }
  RequestBase$$addField(param_1,"appVer",tmp1,0);
  iVar1 = SingletonMonoBehaviour$$get_Instance
                    (Method$SingletonMonoBehaviour_DataManager_.get_Instance());
  if (iVar1 == 0) {
    FUN_003733b8(0);
  }
  uVar2 = DataManager$$getMasterDataVersion(iVar1,0);
  if (param_1 == 0) {
    FUN_003733b8(0);
  }
  RequestBase$$addField(param_1,"dataVer",uVar2,0);
  iVar1 = SingletonMonoBehaviour$$get_Instance
                    (Method$SingletonMonoBehaviour_DataManager_.get_Instance());
  if (iVar1 == 0) {
    FUN_003733b8(0);
  }
  uVar3 = DataManager$$getMasterDateVersion(iVar1,0);
  if (param_1 == 0) {
    FUN_003733b8(0);
  }
  RequestBase$$addField(param_1,"dateVer",(int)((ulonglong)uVar3 >> 0x20),(int)uVar3,0);
  if (((*(byte *)(Class$NetworkManager + 0xbf) & 2) != 0) &&
     (*(int *)(Class$NetworkManager + 0x70) == 0)) {
    FUN_0035803c();
  }
  uVar3 = NetworkManager$$getTime();
  if (param_1 == 0) {
    FUN_003733b8(0);
  }
  RequestBase$$addField(param_1,"lastAccessTime",(int)((ulonglong)uVar3 >> 0x20),(int)uVar3,0);
  tmp1 = Class$ManagerConfig->instance->verCode;
  if (param_1 == 0) {
    FUN_003733b8(0);
  }
  RequestBase$$addField(param_1,"verCode",tmp1,0);
  return;
}
```

this lets me map userId and authKey in the NetworkManager struct


```c
  iVar1 = *(int *)&Class$NetworkManager->instance->userId;
  if (iVar1 != 0) {
    if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
      FUN_0035803c();
      iVar1 = *(int *)&Class$NetworkManager->instance->userId;
    }
    if (param_1 == 0) {
      FUN_003733b8(0);
    }
    RequestBase$$addField(param_1,"userId",iVar1,0);
    uVar2 = *(undefined4 *)&Class$NetworkManager->instance->authKey;
    if (param_1 == 0) {
      FUN_003733b8(0);
    }
    RequestBase$$addField(param_1,"authKey",uVar2,0);
  }
```

if we search for NetworkManager we can find a bunch of getters and setters
we could use to map other fields but we don't care about everything

I mapped a few that looked interesting: GetSecurityServerSetting,
renamed endpointHost to gameServerSetting to match the getter, renamed
assetsEndpoint to dataServerSetting, renamed webviewHost to
webServerSetting, serverSettingType, dataServerFolderName,

`NetworkManager$$getWebUrl` reveals a few query params

```c
    uVar9 = NetworkManager$$getTime();
    pNVar2 = Class$NetworkManager->instance;
    uVar8 = *(undefined4 *)&pNVar2->field_0xac;
    uVar10 = __aeabi_ldivmod((int)((ulonglong)uVar9 >> 0x20),(int)uVar9,
                             *(undefined4 *)&pNVar2->field_0x8,*(undefined4 *)&pNVar2->field_0xc);
    if (param_1 == 0) {
      FUN_003733b8(0);
      iVar3 = String$$IndexOf(0,uVar8,0);
      FUN_003733b8(0);
      iVar1 = 0;
    }
    else {
      iVar3 = String$$IndexOf(param_1,uVar8,0);
      iVar1 = param_1;
    }
    iVar1 = String$$IndexOf(iVar1,"?",0);
    if (iVar3 < 0) {
      if (iVar1 < 0) {
        uVar8 = FUN_00381f7c(Class$long,&local_28);
        local_28 = (undefined4)((ulonglong)uVar9 >> 0x20);
        local_24 = (undefined4)uVar9;
        uVar10 = uVar9;
        if (((*(byte *)(Class$string + 0xbf) & 2) != 0) && (*(int *)(Class$string + 0x70) == 0)) {
          FUN_0035803c();
          local_28 = (undefined4)((ulonglong)uVar10 >> 0x20);
          local_24 = (undefined4)uVar10;
        }
        puVar4 = &"?lastAccessTime=";
      }
      else {
        if (param_1 == 0) {
          FUN_003733b8(0);
        }
        iVar1 = String$$IndexOf(param_1,"lastAccessTime=",0);
        if (-1 < iVar1) {
          return param_1;
        }
        uVar8 = FUN_00381f7c(Class$long,&local_28);
        local_28 = (undefined4)((ulonglong)uVar9 >> 0x20);
        local_24 = (undefined4)uVar9;
        uVar10 = uVar9;
        if (((*(byte *)(Class$string + 0xbf) & 2) != 0) && (*(int *)(Class$string + 0x70) == 0)) {
          FUN_0035803c();
          local_28 = (undefined4)((ulonglong)uVar10 >> 0x20);
          local_24 = (undefined4)uVar10;
        }
        puVar4 = &"&lastAccessTime=";
      }
    }
    else {
      if (iVar1 < 0) {
        uVar8 = FUN_00381f7c(Class$long,&local_28);
        local_28 = (undefined4)((ulonglong)uVar10 >> 0x20);
        local_24 = (undefined4)uVar10;
        if (((*(byte *)(Class$string + 0xbf) & 2) != 0) && (*(int *)(Class$string + 0x70) == 0)) {
          FUN_0035803c();
          local_28 = (undefined4)((ulonglong)uVar10 >> 0x20);
          local_24 = (undefined4)uVar10;
        }
        puVar4 = &"?v=";
      }
      else {
        uVar8 = FUN_00381f7c(Class$long,&local_28);
        local_28 = (undefined4)((ulonglong)uVar10 >> 0x20);
        local_24 = (undefined4)uVar10;
        if (((*(byte *)(Class$string + 0xbf) & 2) != 0) && (*(int *)(Class$string + 0x70) == 0)) {
          FUN_0035803c();
          local_28 = (undefined4)((ulonglong)uVar10 >> 0x20);
          local_24 = (undefined4)uVar10;
        }
        puVar4 = &"&v=";
      }
    }
    param_1 = String$$Concat(param_1,*puVar4,uVar8,0);
    local_28 = (undefined4)((ulonglong)uVar10 >> 0x20);
    local_24 = (undefined4)uVar10;
  }
```

interesting class name in `NetworkManager$$GetMk`

```c
  uVar2 = CatAndMouseGame$$MouseGame1(uVar2,0,0);
  return uVar2;
```

looks like the il2cppdumper guy has already reverse engineered it some time
ago

* https://github.com/Hengle/Fgo
* https://www.perfare.net/629.html

this also obfuscates the value returned by GetCv

these 2 values seem to be retrieved by `MdcStr$$Ec` . I couldn't find
references to this but we can check later if needed

GetApiCode, GetAuthCode are also obfuscated by this

these are called in a huge huge function named
`NetworkManager._RequestCR_c__Iterator1$$MoveNext`

this has a large switch which handles what looks like different types of
http requests

skimming through this we can map a few NetworkManager fields:

```c
  iVar15 = *(int *)&Class$NetworkManager->instance->userAgent;
  if (iVar15 != 0) {
    iVar8 = *(int *)(param_1 + 0x40);
    if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
      FUN_0035803c();
      iVar15 = *(int *)&Class$NetworkManager->instance->userAgent;
    }
    if (iVar8 == 0) {
      FUN_003733b8(0);
    }
    FUN_006eabe0(iVar8,"User-Agent",iVar15,Method$Dictionary_string_-string_.Add());
  }
```

```c
  iVar15 = *(int *)&Class$NetworkManager->instance->cookie;
  if (iVar15 != 0) {
    iVar8 = *(int *)(param_1 + 0x40);
    if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
      FUN_0035803c();
      iVar15 = *(int *)&Class$NetworkManager->instance->cookie;
    }
    if (iVar8 == 0) {
      FUN_003733b8(0);
    }
    FUN_006eabe0(iVar8,"Cookie",iVar15,Method$Dictionary_string_-string_.Add());
  }
```

so it looks like they use their own http library and this iVar8 dict is
being turned into form data:

```c
  uVar2 = WWWForm$$get_data(iVar8,0);
  uVar20 = *(undefined4 *)(param_1 + 0x40);
  uVar18 = thunk_FUN_00382384(Class$DelightWorks.Network.BestWWW);
  BestWWW$$.ctor(uVar18,iVar15,uVar2,uVar20,0);
```

I guess I'll map out the HTTPRequest struct (instantiated in BestWWW)
and maybe hook somewhere and log http traffic

so while googling some error strings in HTTPRequest I found the actual
library they're using, it's called BestHTTP and it's proprietary. 60$ on
the unity asset store. pretty hilarious to spend 60$ and lock yourself into
a proprietary library for a simple http implementation lol

well at least the source is available so I can look at it for reference

the easiest method to hook seems to be `HTTPManager$$SendRequestImpl` .
it has a rather unique name which makes it easy to find by scanning
il2cpp metadata and it takes the HTTPRequest as a param, and it's clearly
called when the request is sent.

for responses `HTTPRequest$$CallCallback` seems perfect

you can find my hooks here: https://github.com/Francesco149/fgohook

some requests take an authCode field. if we take a look again at
`NetworkManager._RequestCR_c__Iterator1$$MoveNext` we see that it calls
GetAuthCode passing it some field of whatever class is passed to this
function.

```c
  pvVar19 = (void *)param_1->field_0x38;
  if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
    FUN_0035803c();
  }
  iVar15 = NetworkManager$$GetAuthCode(pvVar19);
  param_1->field_0x58 = iVar15;
  if (iVar15 != 0) {
    iVar8 = param_1->field_0x3c;
    if (iVar8 == 0) {
      FUN_003733b8(0);
    }
    WWWForm$$AddField(iVar8,"authCode",iVar15,0);
  }
```

I'm pretty sure this is just a dict of the form fields, if we scroll up
we see the same field being passed to getWWWForm:

```c
  iVar15 = RequestBase$$getWWWForm(piVar17,&param_1->field_0x38,0);
  param_1->field_0x3c = iVar15;
```

ok, let's look at GetAuthCode. it took a bit of guessing to figure out
the weird code il2cpp generates for array append/resize, but what it does
is build a query string (might be unescaped, not sure yet) out of the
form fields and then computes the sha1 of `query_string:field_0x50` and
returns the hash as a base64 string.

```c
undefined4 NetworkManager$$GetAuthCode(void *param_1)

{
  Array_string_ *arrayOfStrings;
  String *tmps;
  undefined4 val;
  int it;
  int *piVar1;
  String *str;
  undefined4 key;
  void *pair;
  undefined4 uStack92;
  undefined8 local_48;
  undefined8 uStack64;
  undefined4 local_38;
  void *pair_;
  undefined4 local_2c;
  
  if (DAT_027ee62d == '\0') {
    FUN_003479b0(0x65b2);
    DAT_027ee62d = '\x01';
  }
  local_2c = 0;
  local_48 = 0;
  uStack64 = 0;
  pair_ = (void *)0x0;
  local_38 = 0;
  if (((Class$string->field_0xbf & 2) != 0) && (Class$string->field_0x70 == 0)) {
    FUN_0035803c();
  }
  str = Class$string->staticData->empty;
  if (param_1 == (void *)0x0) {
    throwNullPointer(0);
  }
  SortedDictionary$$GetEnumerator
            (&pair,param_1,Method$SortedDictionary_string_-string_.GetEnumerator());
  while (it = FUN_0201a200(&local_48,Method$SortedDictionary.Enumerator_string_-string_.MoveNext()),
        it != 0) {
    FUN_0201a1ec(&pair,&local_48,Method$SortedDictionary.Enumerator_string_-string_.get_Current());
    local_2c = uStack92;
    pair_ = pair;
    if (((Class$string->field_0xbf & 2) != 0) && (Class$string->field_0x70 == 0)) {
      FUN_0035803c();
    }
    it = String$$op_Inequality(str,Class$string->staticData->empty,0);
    if (it == 0) {
                    /* first iteration only: str=key + "=" + value */
      key = FUN_01dc7cec(&pair_,Method$KeyValuePair_string_-string_.get_Key());
      val = FUN_01dc7cfc(&pair_,Method$KeyValuePair_string_-string_.get_Value());
      if (((Class$string->field_0xbf & 2) != 0) && (Class$string->field_0x70 == 0)) {
        FUN_0035803c();
      }
      str = (String *)String$$Concat(str,key,"=",val,0);
    }
    else {
                    /* this whole block does str="".join([str, "&", key, "=", value]) */
      arrayOfStrings = (Array_string_ *)InstantiateArray(Class$string[],5);
      if (arrayOfStrings == (Array_string_ *)0x0) {
        throwNullPointer(0);
      }
      if ((str != (String *)0x0) && (it = FUN_003822bc(str,arrayOfStrings->vtable[8]), it == 0)) {
        key = FUN_00374a74();
        throw(key,0,0);
      }
      if (arrayOfStrings->length == 0) {
        key = FUN_00374328();
        throw(key,0,0);
      }
      arrayOfStrings->data[0] = str;
      if (("&" != (String *)0x0) && (it = FUN_003822bc("&",arrayOfStrings->vtable[8]), it == 0)) {
        key = FUN_00374a74();
        throw(key,0,0);
      }
      tmps = "&";
      if ((uint)arrayOfStrings->length < 2) {
        key = FUN_00374328();
        throw(key,0,0);
      }
      arrayOfStrings->data[1] = tmps;
      tmps = (String *)FUN_01dc7cec(&pair_,Method$KeyValuePair_string_-string_.get_Key());
      if ((tmps != (String *)0x0) && (it = FUN_003822bc(tmps,arrayOfStrings->vtable[8]), it == 0)) {
        key = FUN_00374a74();
        throw(key,0,0);
      }
      if ((uint)arrayOfStrings->length < 3) {
        key = FUN_00374328();
        throw(key,0,0);
      }
      arrayOfStrings->data[2] = tmps;
      if (("=" != (String *)0x0) && (it = FUN_003822bc("=",arrayOfStrings->vtable[8]), it == 0)) {
        key = FUN_00374a74();
        throw(key,0,0);
      }
      tmps = "=";
      if ((uint)arrayOfStrings->length < 4) {
        key = FUN_00374328();
        throw(key,0,0);
      }
      arrayOfStrings->data[3] = tmps;
      tmps = (String *)FUN_01dc7cfc(&pair_,Method$KeyValuePair_string_-string_.get_Value());
      if ((tmps != (String *)0x0) && (it = FUN_003822bc(tmps,arrayOfStrings->vtable[8]), it == 0)) {
        key = FUN_00374a74();
        throw(key,0,0);
      }
      if ((uint)arrayOfStrings->length < 5) {
        key = FUN_00374328();
        throw(key,0,0);
      }
      arrayOfStrings->data[4] = tmps;
      if (((Class$string->field_0xbf & 2) != 0) && (Class$string->field_0x70 == 0)) {
        FUN_0035803c();
      }
      str = (String *)String$$Concat(arrayOfStrings,0);
    }
  }
  FUN_0201a400(&local_48,Method$SortedDictionary.Enumerator_string_-string_.Dispose());
  if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
    FUN_0035803c();
  }
  if (*(int *)&Class$NetworkManager->instance->field_0x50 == 0) {
    key = 0;
  }
  else {
    it = thunk_FUN_00382384(Class$System.Security.Cryptography.SHA1CryptoServiceProvider);
    SHA1CryptoServiceProvider$$.ctor(it,0);
    piVar1 = (int *)thunk_FUN_00382384(Class$System.Text.UTF8Encoding);
    UTF8Encoding$$.ctor(piVar1,0);
    if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
      FUN_0035803c();
    }
    key = *(undefined4 *)&Class$NetworkManager->instance->field_0x50;
    if (((Class$string->field_0xbf & 2) != 0) && (Class$string->field_0x70 == 0)) {
      FUN_0035803c();
    }
    key = String$$Concat(str,":",key,0);
    if (piVar1 == (int *)0x0) {
      throwNullPointer(0);
    }
    key = (**(code **)(*piVar1 + 0x110))(piVar1,key,*(undefined4 *)(*piVar1 + 0x114));
    if (it == 0) {
      it = 0;
      throwNullPointer(0);
      key = HashAlgorithm$$ComputeHash(0,key,0);
      throwNullPointer(0);
    }
    else {
      key = HashAlgorithm$$ComputeHash(it,key,0);
    }
    HashAlgorithm$$Clear(it,0);
    if (((*(byte *)(Class$System.Convert + 0xbf) & 2) != 0) &&
       (*(int *)(Class$System.Convert + 0x70) == 0)) {
      FUN_0035803c();
    }
    key = Convert$$ToBase64String(key,0);
  }
  return key;
}
```

great, now let's look for references to field 0x50 and see where it comes
from

```c
void NetworkManager$$SetAuth(undefined4 param_1,int param_2,undefined4 param_3,undefined4 param_4)

{
  astruct_1 *paVar1;
  
  if (DAT_027ee63a == '\0') {
    FUN_003479b0(0x65dd);
    DAT_027ee63a = '\x01';
  }
  if (param_2 == 0) {
    return;
  }
  if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
    FUN_0035803c();
  }
  paVar1 = Class$NetworkManager;
  *(int *)&Class$NetworkManager->instance->userId = param_2;
  *(undefined4 *)&paVar1->instance->authKey = param_3;
  *(undefined4 *)&paVar1->instance->field_0x50 = param_4;
  return;
}
```

this is called from `AccountRegistRequest$$requestCompleted`

```c
    item = (int *)FUN_006e96c4(iVar1,"userId",Method$Dictionary_string_-object_.get_Item());
    if (item == (int *)0x0) {
      throwNullPointer(0);
    }
    userId = (**(code **)(*item + 0xd8))(item,*(undefined4 *)(*item + 0xdc));
    item = (int *)FUN_006e96c4(iVar1,"authKey",Method$Dictionary_string_-object_.get_Item());
    if (item == (int *)0x0) {
      throwNullPointer(0);
    }
    authKey = (**(code **)(*item + 0xd8))(item,*(undefined4 *)(*item + 0xdc));
    item = (int *)FUN_006e96c4(iVar1,"secretKey",Method$Dictionary_string_-object_.get_Item());
    if (item == (int *)0x0) {
      throwNullPointer(0);
    }
    secretKey = (**(code **)(*item + 0xd8))(item,*(undefined4 *)(*item + 0xdc));
    iVar1 = SingletonMonoBehaviour$$get_Instance
                      (Method$SingletonMonoBehaviour_NetworkManager_.get_Instance());
    if (iVar1 == 0) {
      throwNullPointer(0);
    }
    NetworkManager$$SetAuth(iVar1,userId,authKey,secretKey,0);
```

okay, it's just the secretKey. pretty straightforward. I implemented this
and tested it and sure enough creating accounts works, it's only a matter
at looking at the http log from my hooks and mimick those requests

so the login request takes a few interesting fields:

```c
void TopLoginRequest$$beginRequest(int param_1)

{
  uint y;
  undefined4 dataServerFolder;
  int *utf8;
  undefined4 str;
  uint dataServerFolderCrc32;
  uint userId;
  uint x;
  int userState;
  undefined8 lastAccessTime;
  
  if (DAT_027eee68 == '\0') {
    FUN_003479b0(0xa033);
    DAT_027eee68 = '\x01';
  }
  RequestBase$$addBaseField(param_1,0);
  if (((Class$NetworkManager->field_0xbf & 2) != 0) && (Class$NetworkManager->field_0x70 == 0)) {
    FUN_0035803c();
  }
  dataServerFolder = NetworkManager$$GetDataServerFolderName(0);
  if (((*(byte *)(Class$System.Text.Encoding + 0xbf) & 2) != 0) &&
     (*(int *)(Class$System.Text.Encoding + 0x70) == 0)) {
    FUN_0035803c();
  }
  utf8 = (int *)Encoding$$get_UTF8(0);
  if (utf8 == (int *)0x0) {
    throwNullPointer(0);
  }
  str = (**(code **)(*utf8 + 0x110))(utf8,dataServerFolder,*(undefined4 *)(*utf8 + 0x114));
  if (((*(byte *)(Class$Crc32 + 0xbf) & 2) != 0) && (*(int *)(Class$Crc32 + 0x70) == 0)) {
    FUN_0035803c();
  }
  dataServerFolderCrc32 = Crc32$$Compute(str,0);
  userId = NetworkManager$$get_UserId(0);
  userState = *(int *)(param_1 + 0x10);
  if (userState == 0) {
    throwNullPointer(0);
  }
  str = FUN_006e96c4(userState,"lastAccessTime",Method$Dictionary_string_-string_.get_Item());
  lastAccessTime = Int64$$Parse(str,0);
  x = ~(uint)((ulonglong)lastAccessTime >> 0x20);
  y = -((int)~(uint)lastAccessTime >> 0x1f);
  userState = ~(uint)lastAccessTime + (uint)CARRY4(x,y);
  str = 0;
                    /* ^ this is probably a 64-bit operation
                       CARRY4(x,y) - true if there would be a carry adding x to y
                       
                       addField takes loword and hiword for a 64-bit int */
  RequestBase$$addField
            (param_1,"userState",
             (x + y >> 2 | userState * 0x40000000) ^ userId & dataServerFolderCrc32,userState >> 2);
  RequestBase$$addField(param_1,"assetbundleFolder",dataServerFolder,0,str);
  dataServerFolder = NetworkManager$$GetTerminalDispState(0);
  RequestBase$$addField(param_1,"isTerminalLogin",dataServerFolder,0);
  NetworkManager$$RequestStart(param_1,0);
  return;
}
```

`NetworkManager$$GetTerminalDispState` is just some check on the scene id,
we can probably just hardcode it for each request

let's find out how dataServerFolderName is generated

in `TopGameDataRequest$$requestCompleted` :

```c
    iVar2 = FUN_006eb2a0(iVar1,"assetbundle",Method$Dictionary_string_-object_.ContainsKey());
    if (iVar2 == 1) {
      piVar3 = (int *)FUN_006e96c4(iVar1,"assetbundle",Method$Dictionary_string_-object_.get_Item())
      ;
      if (piVar3 == (int *)0x0) {
        throwNullPointer(0);
      }
      uVar5 = (**(code **)(*piVar3 + 0xd8))(piVar3,*(undefined4 *)(*piVar3 + 0xdc));
      if (((*(byte *)(Class$System.Convert + 0xbf) & 2) != 0) &&
         (*(int *)(Class$System.Convert + 0x70) == 0)) {
        FUN_0035803c();
      }
      pAVar6 = (Array *)Convert$$FromBase64String(uVar5,0);
      if (((Class$CatAndMouseGame->field_0xbf & 2) != 0) && (Class$CatAndMouseGame->field_0x70 == 0)
         ) {
        FUN_0035803c();
      }
      uVar5 = CatAndMouseGame$$MouseInfoMsgPack(pAVar6);
      if (((*(byte *)(Class$JsonManager + 0xbf) & 2) != 0) &&
         (*(int *)(Class$JsonManager + 0x70) == 0)) {
        FUN_0035803c();
      }
      iVar2 = JsonManager$$getDictionary(uVar5,0);
      if (iVar2 != 0) {
        iVar7 = FUN_006eb2a0(iVar2,"folderName",Method$Dictionary_string_-object_.ContainsKey());
        if (iVar7 == 1) {
          piVar3 = (int *)FUN_006e96c4(iVar2,"folderName",
                                       Method$Dictionary_string_-object_.get_Item());
          if (piVar3 == (int *)0x0) {
            throwNullPointer(0);
          }
          uVar5 = (**(code **)(*piVar3 + 0xd8))(piVar3,*(undefined4 *)(*piVar3 + 0xdc));
          if (((Class$NetworkManager->field_0xbf & 2) != 0) &&
             (Class$NetworkManager->field_0x70 == 0)) {
            FUN_0035803c();
          }
          NetworkManager$$SetDataServerFolderName(uVar5,0);
        }
        iVar7 = FUN_006eb2a0(iVar2,"animalName",Method$Dictionary_string_-object_.ContainsKey());
        if (iVar7 == 1) {
          piVar3 = (int *)FUN_006e96c4(iVar2,"animalName",
                                       Method$Dictionary_string_-object_.get_Item());
          if (piVar3 == (int *)0x0) {
            throwNullPointer(0);
          }
          uVar5 = (**(code **)(*piVar3 + 0xd8))(piVar3,*(undefined4 *)(*piVar3 + 0xdc));
          if (((Class$CatAndMouseGame->field_0xbf & 2) != 0) &&
             (Class$CatAndMouseGame->field_0x70 == 0)) {
            FUN_0035803c();
          }
          CatAndMouseGame$$ThirdHomeBuilding(uVar5,0);
        }
        iVar7 = FUN_006eb2a0(iVar2,"zooName",Method$Dictionary_string_-object_.ContainsKey());
        if (iVar7 == 1) {
          piVar3 = (int *)FUN_006e96c4(iVar2,"zooName",Method$Dictionary_string_-object_.get_Item())
          ;
          if (piVar3 == (int *)0x0) {
            throwNullPointer(0);
          }
          uVar5 = (**(code **)(*piVar3 + 0xd8))(piVar3,*(undefined4 *)(*piVar3 + 0xdc));
          if (((Class$CatAndMouseGame->field_0xbf & 2) != 0) &&
             (Class$CatAndMouseGame->field_0x70 == 0)) {
            FUN_0035803c();
          }
          CatAndMouseGame$$ForthHomeBuilding(uVar5,0);
        }
      }
    }
```

looks like this is where that CatAndMouseGame class comes into play,
it decodes and gets some parameters from assetbundle field

not an issue, CatAndMouseGame has already been reversed and it wouldn't
be hard to reverse it myself.

```c
void CatAndMouseGame$$MouseInfoMsgPack(Array *data)

{
  astruct_4 *catAndMouse;
  undefined4 tmp;
  int *piVar1;
  Array *rgbKey;
  
  if (DAT_027ee855 == '\0') {
    FUN_003479b0(0x1d2d);
    DAT_027ee855 = '\x01';
  }
  if (data == (Array *)0x0) {
    throwNullPointer(0);
  }
  tmp = InstantiateArray(Class$byte[],data->length + -0x20);
  if (((*(byte *)(Class$System.Text.Encoding + 0xbf) & 2) != 0) &&
     (*(int *)(Class$System.Text.Encoding + 0x70) == 0)) {
    FUN_0035803c();
  }
  piVar1 = (int *)Encoding$$get_UTF8(0);
  if (piVar1 == (int *)0x0) {
    throwNullPointer(0);
  }
  rgbKey = (Array *)(**(code **)(*piVar1 + 0x110))
                              (piVar1,"W0Juh4cFJSYPkebJB9WpswNF51oa6Gm7",
                               *(undefined4 *)(*piVar1 + 0x114));
  if (((Class$CatAndMouseGame->field_0xbf & 2) != 0) && (Class$CatAndMouseGame->field_0x70 == 0)) {
    FUN_0035803c();
  }
  catAndMouse = Class$CatAndMouseGame;
  Class$CatAndMouseGame->staticData->rgbKey = rgbKey;
                    /* void Copy (Array sourceArray, long sourceIndex, Array destinationArray, long
                       destinationIndex, long length) */
  Array$$Copy(data,0,catAndMouse->staticData->rgbIV,0,0x20,0);
  Array$$Copy(data,0x20,tmp,0,data->length + -0x20,0);
  CatAndMouseGame$$MouseHomeMsgPack
            (tmp,Class$CatAndMouseGame->staticData->rgbKey,Class$CatAndMouseGame->staticData->rgbIV,
             1);
  return;
}
```

I already looked ahead and I know those 2 params are rgbKey and rgbIV
for the decryptor. so the first 32 bytes of the data are the IV, the rest
is the data and the rgbKey is a fixed string

here they use this library: https://github.com/shogo82148/MiniMessagePack

to decode MsgPack data

```c
void CatAndMouseGame$$MouseHomeMsgPack(Array *data,Array *rgbKey,Array *rgbIV,bool param_4)

{
  int packer;
  undefined4 msgPackData;
  
  if (DAT_027ee869 == '\0') {
    FUN_003479b0(0x1d2a);
    DAT_027ee869 = '\x01';
  }
  packer = thunk_FUN_00382384(Class$MiniMessagePack.MiniMessagePacker);
  MiniMessagePacker$$.ctor(packer,0);
  if (((Class$CatAndMouseGame->field_0xbf & 2) != 0) && (Class$CatAndMouseGame->field_0x70 == 0)) {
    FUN_0035803c();
  }
  msgPackData = CatAndMouseGame$$MouseHomeSub(data,rgbKey,rgbIV,param_4);
  if (packer == 0) {
    throwNullPointer(0);
  }
  MiniMessagePacker$$Unpack(packer,msgPackData,0);
  return;
}
```

MouseHomeSub looks exactly like MouseHomeMain in that Fgo repository
https://github.com/Hengle/Fgo/blob/master/CatAndMouseGame.cs#L261

```c
Array * CatAndMouseGame$$MouseHomeSub(Array *data,Array *rgbKey,Array *rgbIV,bool isPress)

{
  undefined4 transform;
  Array *buffer;
  int *stream2;
  int *stream3;
  int *stream5;
  Array *buffer2;
  int iVar1;
  int *stream;
  undefined4 auStack56 [2];
  undefined4 *local_30;
  int *local_2c;
  
  if (DAT_027ee86f == '\0') {
    FUN_003479b0(0x1d2b);
    DAT_027ee86f = '\x01';
  }
  local_30 = auStack56;
  local_2c = (int *)0x0;
  stream = (int *)thunk_FUN_00382384(Class$System.Security.Cryptography.RijndaelManaged);
  RijndaelManaged$$.ctor(stream,0);
  if (stream == (int *)0x0) {
    throwNullPointer(0);
  }
                    /* PaddingMode.PKCS7 */
  (**(code **)(*stream + 0x168))(stream,2,*(undefined4 *)(*stream + 0x16c));
                    /* CipherMode.CBC */
  (**(code **)(*stream + 0x158))(stream,1,*(undefined4 *)(*stream + 0x15c));
                    /* KeySize = 0x100 */
  (**(code **)(*stream + 0x138))(stream,0x100,*(undefined4 *)(*stream + 0x13c));
                    /* BlockSize = 0x100 */
  (**(code **)(*stream + 0xf8))(stream,0x100,*(undefined4 *)(*stream + 0xfc));
                    /* CreateDecryptor */
  transform = (**(code **)(*stream + 0x178))(stream,rgbKey,rgbIV,*(undefined4 *)(*stream + 0x17c));
  if (data == (Array *)0x0) {
    throwNullPointer(0);
  }
  buffer = (Array *)InstantiateArray(Class$byte[],data->length);
  stream = (int *)thunk_FUN_00382384(Class$System.IO.MemoryStream);
  MemoryStream$$.ctor(stream,data,0);
  stream2 = (int *)thunk_FUN_00382384(Class$System.Security.Cryptography.CryptoStream);
  CryptoStream$$.ctor(stream2,stream,transform,0,0);
  if (buffer == (Array *)0x0) {
    throwNullPointer(0);
  }
  if (stream2 == (int *)0x0) {
    throwNullPointer(0);
  }
                    /* Read */
  (**(code **)(*stream2 + 0x158))(stream2,buffer,0,buffer->length,*(undefined4 *)(*stream2 + 0x15c))
  ;
  if (isPress != false) {
    local_2c = stream;
    stream3 = (int *)thunk_FUN_00382384(Class$System.IO.MemoryStream);
    MemoryStream$$.ctor(stream3,0);
    stream = (int *)thunk_FUN_00382384(Class$System.IO.MemoryStream);
    MemoryStream$$.ctor(stream,buffer,0);
    stream5 = (int *)thunk_FUN_00382384(Class$ICSharpCode.SharpZipLib.GZip.GZipInputStream);
    GZipInputStream$$.ctor(stream5,stream,0);
    buffer2 = (Array *)InstantiateArray(Class$byte[],0x4000);
    while( true ) {
      if (buffer2 == (Array *)0x0) {
        throwNullPointer(0);
      }
      if (stream5 == (int *)0x0) {
        throwNullPointer(0);
      }
                    /* Read */
      iVar1 = (**(code **)(*stream5 + 0x158))
                        (stream5,buffer2,0,buffer2->length,*(undefined4 *)(*stream5 + 0x15c));
      if (iVar1 < 1) break;
      if (stream3 == (int *)0x0) {
        throwNullPointer(0);
      }
                    /* Write */
      (**(code **)(*stream3 + 0x178))(stream3,buffer2,0,iVar1,*(undefined4 *)(*stream3 + 0x17c));
    }
                    /* Close */
    (**(code **)(*stream5 + 0x128))(stream5,*(undefined4 *)(*stream5 + 300));
    if (stream3 == (int *)0x0) {
      throwNullPointer(0);
    }
                    /* ToArray */
    buffer = (Array *)(**(code **)(*stream3 + 0x1c0))(stream3,*(undefined4 *)(*stream3 + 0x1c4));
    if (stream == (int *)0x0) {
      throwNullPointer(0);
    }
                    /* Close */
    (**(code **)(*stream + 0x128))(stream,*(undefined4 *)(*stream + 300));
    stream = local_2c;
                    /* Close */
    (**(code **)(*stream3 + 0x128))(stream3,*(undefined4 *)(*stream3 + 300));
  }
  *local_30 = 0xfc;
  if (stream != (int *)0x0) {
    (**(code **)(*stream + 0x128))(stream,*(undefined4 *)(*stream + 300));
  }
  if (stream2 != (int *)0x0) {
    (**(code **)(*stream2 + 0x128))(stream2,*(undefined4 *)(*stream2 + 300));
  }
  return buffer;
}
```

yeah, this shouldn't be a problem to implement, just a bit tedious to
stitch together

to be continued...
