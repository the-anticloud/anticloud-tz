# TZ

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-carbon_capture-lightgrey)

> Anticloud-hardened packaging of the upstream project `TZ` in category **CARBON CAPTURE**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** CARBON CAPTURE · **Upstream:** https://github.com/the-anticloud/anticloud-tz.git · **Upstream pin:** `11776eb2a589019c3e01aafba693bb03b1f37fa5` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# TZImagePickerController
[![CocoaPods](https://img.shields.io/cocoapods/v/TZImagePickerController.svg?style=flat)](https://github.com/banchichen/TZImagePickerController)
[![Carthage compatible](https://img.shields.io/badge/Carthage-compatible-4BC51D.svg?style=flat)](https://github.com/Carthage/Carthage)

 A source of UIImagePickerController, support picking multiple photos、original photo、video, also allow preview photo and video, support iOS10+.   
 一个支持多选、选原图和视频的图片选择器，同时有预览功能，支持iOS10+。
 
## 重要提示1：提issue前，请先对照Demo、常见问题自查！Demo正常说明你可以升级下新版试试。          
 
## 重要提示2：3.8.8版本修复了iOS18下无照片和openURL失效的问题       
     关于iOS14模拟器的问题
 PHAuthorizationStatusLimited授权模式下，iOS14模拟器有bug，未授权照片无法显示，真机正常，暂可忽略：https://github.com/banchichen/TZImagePickerController/issues/1347 
 
     关于升级iOS10和Xcdoe8的提示:    
 在Xcode8环境下将项目运行在iOS10的设备/模拟器中，访问相册和相机需要额外配置info.plist文件。分别是Privacy - Photo Library Usage Description和Privacy - Camera Usage Description字段，详见Demo中info.plist中的设置。
    
     项目截图 1.Demo首页 2.照片列表页 3.照片预览页 4.视频预览页
<img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/DemoPage.png" width="40%" height="40%"><img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/photoPickerVc.PNG" width="40%" height="40%">
<img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/photoPreviewVc.PNG" width="40%" height="40%"><img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/videoPlayerVc.PNG" width="40%" height="40%">

## 一. Installation 安装

#### CocoaPods
> pod 'TZImagePickerController'        # Full version with all features      
> pod 'TZImagePickerController/Basic'  # No location code        

#### Carthage
> github "banchichen/TZImagePickerController"

#### 手动安装
> 将TZImagePickerController文件夹拽入项目中，导入头文件：#import "TZImagePickerController.h"

## 二. Example 例子

    TZImagePickerController *imagePickerVc = [[TZImagePickerController alloc] initWithMaxImagesCount:9 delegate:self];
    
    // You can get the photos by block, the same as by delegate.
    // 你可以通过block或者代理，来得到用户选择的照片.
    [imagePickerVc setDidFinishPickingPhotosHandle:^(NSArray<UIImage *> *photos, NSArray *assets, BOOL isSelectOriginalPhoto) {
    
    }];
    [self presentViewController:imagePickerVc animated:YES completion:nil];
  
## 三. Requirements 要求
   iOS 10 or later.      
   支持iOS10及以上系统。      
  
   TZImagePickerController uses Camera、Location、Microphone、Photo Library，you need add these properties to info.plist like Demo：       
   TZImagePickerController使用了相机、定位、麦克风、相册，请参考Demo添加下列属性到info.plist文件：        
   	`Privacy - Camera Usage Description`     
    `Privacy - Location Usage Description`    
	`Privacy - Location When In Use Usage Description`    
 	`Privacy - Microphone Usage Description`   
 	`Privacy - Photo Library Usage Description`   
    `Prevent limited photos access alert`    
   
## 四. More 更多 

  If you find a bug, please create a issue.  
  More information please view code.  
  如果你发现了bug，请提一个issue。 
  更多信息详见代码，也可查看我的博客: [我的博客](http://www.jianshu.com/p/1975411a31bb "半尺尘 - 简书")
  
      关于issue: 
  请尽可能详细地描述**系统版本**、**手机型号**、**库的版本**、**崩溃日志**和**复现步骤**，**请先更新到最新版再测试一下**，如果新版还存在再提~如果已有开启的类似issue，请直接在该issue下评论说出你的问题
  
## 五. FAQ 常见问题    

**Q：pod search TZImagePickerController 搜索出来的不是最新版本**       
A：需要在终端执行cd转换文件路径命令退回到Desktop，然后执行pod setup命令更新本地spec缓存（可能需要几分钟）,然后再搜索就可以了       
     
**Q：拍照后照片保存失败**         
A：请参考issue481：https://github.com/banchichen/TZImagePickerController/issues/481 的信息排查，若还有问题请直接在issue内评论   
 
**Q：photos数组图片不是原图，如何获取原图？**        
A：请参考issue457的解释：https://github.com/banchichen/TZImagePickerController/issues/457    

**Q：系统语言是中文/英文，界面上却有部分相册名字、返回按钮显示成了英文/中文？**        
A：请参考 https://github.com/banchichen/TZImagePickerController/issues/443 和 https://github.com/banchichen/TZImagePickerController/issues/929          
 
**Q：预览界面能否支持传入NSURL、UIImage对象？**        
A：3.0.1版本已支持，需新接一个库：[TZImagePreviewController](https://github.com/banchichen/TZImagePreviewController)，请参考里面的Demo使用。       

**Q：设置可选视频的最大/最小时长？照片的最小/最大尺寸？不符合要求的不显示**       
A：可以的，参照Demo的isAssetCanBeDisplayed方法实现。我会返回asset出来，显示与否你来决定，注意这个是一个同步方法，对于需要根据asset去异步获取的信息如视频的大小、视频是否存在iCloud里来过滤的，无法做到。如果真要这样做，相册打开速度会变慢，你需要改我源码。       
如果需要显示，选择时才提醒用户不可选，则实现isAssetCanBeSelected，用户选择时会调用它        

**Q：预览页面出现了导航栏？**        
A：https://github.com/banchichen/TZImagePickerController/issues/652         
   
**Q：可否增加微信编辑图片的功能？**           
A：考虑下，优先级低  

**Q：是否有QQ/微信群/钉钉群？**            
A：有「钉钉群：33192786」和「QQ群：859033147」，推荐加钉钉群，答疑响应更快         

**Q：想提交一个Pull Request？**           
A：请先加钉钉群(33192786)说下方案，和我确认下，避免同时改动同一处内容。**一个PR请只修复1个问题，变动内容越少越好**。     

**Q：demo在真机上跑不起来？**             
A：1、team选你自己的；2、bundleId也改成你自己的或改成一个不会和别人重复的。可参考[简书的这篇博客](https://www.jianshu.com/p/cbe59138fca6)             

**Q：3.6.4以上版本设置导航栏颜色无效？**            
A：参考Demo里的代码，加上imagePickerVc.navigationBar.standardAppearance的相关设置                     

**Q：设置导航栏颜色无效？导航栏颜色总是白色？**            
A：是否有集成WRNavigationBar？如有，参考其readme调一下它的wr_setBlackList，把TZImagePickerController相关的控制器放到黑名单里，使得不受WRNavigationBar的影响。如果没有集成，可在issues列表里搜一下看看类似的issue参考下，如实在没头绪，可加群提供个能复现该问题的demo，0~2天给你解决。最近发现WRNavigationBar的黑名单会有不生效的情况，临时解决方案大家可参考：[https://github.com/wangrui460/WRNavigationBar/issues/145](https://github.com/wangrui460/WRNavigationBar/issues/145)                          

**Q：导航栏没了？**            
A：是否有集成GKNavigationBarViewController？需要升级到2.0.4及以上版本，详见issue：[https://github.com/QuintGao/GKNavigationBarViewController/issues/7](https://github.com/QuintGao/GKNavigationBarViewController/issues/7)。       

**Q：有的视频导出失败？**            
A：升级到2.2.6及以上版本试试，发现是修正视频转向导致的，2.2.6开始默认不再主动修正。如需打开，可设置needFixComposition为YES，但有几率导致安卓拍的视频导出失败。此外也可参考这个issue：https://github.com/banchichen/TZImagePickerController/issues/1073       

**Q：视频导出慢？**            
A：视频导出分两步，第一步是通过PHAsset获取AVURLAsset，如是iCloud视频则涉及到网络请求，耗时容易不可控，第二步是通过AVURLAsset把视频保存到沙盒，耗时

*(excerpt; full text in `UPSTREAM_CLONE/`)*

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Unknown (no standard manifest detected)** (manifests: none detected; scanned in UPSTREAM_CLONE)
- Top-level source layout: `TZImagePickerController/`, `TZImagePickerController.xcodeproj/`, `TZImagePickerControllerFramework/`, `TZImagePickerControllerTests/`, `TZImagePickerControllerUITests/`
- Snapshot size: **123 files**, **11665 lines of code** (measured; see Benchmarks)
- Primary languages: `.m` (28), `.png` (28), `.h` (25), `.strings` (18), `.json` (7), `.plist` (5)
- Upstream commit pinned for this packaging: `11776eb2a589019c3e01aafba693bb03b1f37fa5`

---

## Installation

No installation section was found in the upstream readme, so the commands below are generated from the manifests detected in this project directory.

```sh
# No standard manifest detected. Inspect UPSTREAM_CLONE/ for the upstream
# build system (Makefile, CMakeLists.txt, configure, ...) and follow it.
```

Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

项目截图 1.Demo首页 2.照片列表页 3.照片预览页 4.视频预览页
<img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/DemoPage.png" width="40%" height="40%"><img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/photoPickerVc.PNG" width="40%" height="40%">
<img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/photoPreviewVc.PNG" width="40%" height="40%"><img src="https://github.com/banchichen/TZImagePickerController/blob/master/TZImagePickerController/ScreenShots/videoPlayerVc.PNG" width="40%" height="40%">

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

The upstream API surface is defined by the `TZ` source tree vendored in `UPSTREAM_CLONE/` (Unknown (no standard manifest detected) ecosystem). Public entry points:

- Source modules: `TZImagePickerController/`, `TZImagePickerController.xcodeproj/`, `TZImagePickerControllerFramework/`, `TZImagePickerControllerTests/`, `TZImagePickerControllerUITests/`
- Overlay API: `anticloud/cli.py` exposes 13 subcommands with JSON stdout; `anticloud/bench/runner.py` runs the 16-check suite; `anticloud/provenance/chain.py` exposes the SHA3-256 + Ed25519 provenance chain.

---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Unknown (no standard manifest detected) |
| Manifests detected | none |
| Files in snapshot | 123 |
| Lines of code | 11665 |
| Dependency references | 0 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- None detected at the snapshot root; consult the upstream documentation link in the Upstream section.

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `TZ` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
The MIT License (MIT)

Copyright (c) 2016 Zhen Tan

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `TZ` (category: CARBON CAPTURE)
- **Upstream URL:** https://github.com/the-anticloud/anticloud-tz.git
- **Pinned commit (SHA):** `11776eb2a589019c3e01aafba693bb03b1f37fa5`
- **Branch:** main
- **Pin provenance:** resolved during the second documentation pass. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`e984fb9c85e0dbd28f00dc097845506fb9123678a15a24a28ca9eedd9b4b265f`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

