# 番茄时钟 · Pomodoro Timer

> 一个极简、无广告、体积仅 **28 KB** 的安卓番茄钟，兼容 **Android 4.4 (API 19)** 及以上。
> A minimal, ad-free Pomodoro timer of just **28 KB**, running on **Android 4.4 (API 19)** and above.

---

## 简介 · Introduction

**中文**：番茄时钟是一款为"自己用、简洁、稳定、可靠"而生的计时工具。它没有花哨界面，不联网、不收集任何隐私、没有任何广告，启动即用。最大的特点是**体积只有 28 KB**——比一张手机截图还小，对老机型、低存储设备极其友好。

**English**: Pomodoro Timer is a no-nonsense focus tool built to be simple, stable and reliable. No fancy UI, no network access, no privacy collection, no ads — just open and use. Its headline feature is the **28 KB size** — smaller than a single phone screenshot, perfect for old devices and tight storage.

---

## 功能特性 · Features

- **计时节奏 / Sessions**：专注 45 分钟、短休 10 分钟、长休 15 分钟，每完成 4 个专注进入一次长休（均可在设置中修改）。
  Focus 45 min, short break 10 min, long break 15 min, long break after every 4 focus sessions (all editable in settings).
- **息屏也准时 / Exact alarm**：使用系统级精准闹钟 `AlarmManager.setExactAndAllowWhileIdle()`，息屏、Doze 省电模式下依然准时响铃。
  Uses system-level exact alarm; fires on time even with screen off / Doze mode.
- **系统铃声 + 震动 / Sound & vibration**：调用系统闹钟铃声（`RingtoneManager.TYPE_ALARM`）+ 系统震动，无需自带音频文件。
  Plays the system alarm ringtone + vibrates; no bundled audio needed.
- **后台不被杀 / Background-safe**：计时由系统闹钟托管，进程被杀也不丢节奏。
  Timing is delegated to the system alarm, so it survives process death.
- **大字体不串行 / Auto-scaling**：秒数随系统字号自动缩放，大字体或旧机型下不会换行错位。
  The clock auto-scales with system font size; no wrap on large fonts / old devices.
- **中英双语 / Bilingual UI**：界面跟随系统语言自动切换（中文 / English）。
  UI follows the system language automatically.
- **纯净权限 / Privacy-first**：仅需闹钟、震动、通知权限，**不含任何联网权限**，离线可用、零追踪。
  Only alarm / vibration / notification permissions; **no internet permission**, fully offline and untracked.

---

## 为什么只有 28 KB？· Why only 28 KB?

**中文**：主流安卓应用常用 Kotlin + AndroidX/Material 组件库开发，这些库会整包打进 APK，动辄几 MB。本应用反其道而行——**纯 Java 编写，只调用安卓系统自带的原生框架（`android.widget.*`），零第三方依赖**，因此 APK 不含任何多余代码与资源，体积压缩到极致，同时天然兼容到 Android 4.4。

**English**: Modern apps usually ship with Kotlin + AndroidX/Material libraries bundled into the APK, easily several MB. This app goes the opposite way — **written in pure Java, using only the built-in Android framework (`android.widget.*`), with zero third-party dependencies**. The APK carries no extra code or resources, shrinking to the extreme while staying compatible down to Android 4.4.

---

## 下载与安装 · Download & Install

1. 在 [Releases](../../releases) 页面下载 `番茄时钟-兼容4.4.apk`（28 KB）。
   Download `番茄时钟-兼容4.4.apk` (28 KB) from the [Releases](../../releases) page.
2. 将 APK 传到手机，允许"未知来源"安装，点击安装即可（已使用 debug 签名，可直接安装）。
   Transfer the APK to your phone, allow "Install from unknown sources", and tap to install (debug-signed, installs directly).

> 旧的 `番茄时钟-debug.apk`（5.4 MB，仅支持 Android 7.0+）已弃用，请使用新版。
> The old `番茄时钟-debug.apk` (5.4 MB, Android 7.0+ only) is deprecated — use the new build.

---

## 从源码构建 · Build from Source

环境要求 / Requirements: JDK 21、Android SDK（compileSdk 37 / build-tools 36）、Gradle 8.14.1、Android Gradle Plugin 8.13.2。

```bash
export JAVA_HOME=/path/to/jdk21
export ANDROID_HOME=/path/to/Android/Sdk
cd PomodoroApp
/path/to/gradle-8.14.1/bin/gradle assembleDebug --no-daemon
```

产物位于 / Output: `PomodoroApp/app/build/outputs/apk/debug/app-debug.apk`（开启 R8 压缩 / R8 shrink enabled）。

---

## 权限说明 · Permissions

| 权限 Permission | 用途 Purpose |
|---|---|
| 精准闹钟 Exact alarm | 准时提醒 Scheduled reminders |
| 震动 Vibration | 震动提醒 Vibrate on alert |
| 通知 Notification | 前台计时状态 Status notification |

**不包含任何联网、定位、存储等敏感权限。** / **No internet, location, or storage permissions at all.**

---

## 版权与联系 · Copyright & Contact

© 2026 韩析同 (BD7JQD). 保留所有权利。 / All rights reserved.

- 邮箱 Email: [xitonghan@139.com](mailto:xitonghan@139.com)
- 微信 / WeChat: BD7JQD

---

## 许可证 · License

本项目以 **MIT License** 发布，可自由使用、修改与再分发，请保留上述版权声明。
Released under the **MIT License** — free to use, modify and redistribute; please keep the copyright notice above.
