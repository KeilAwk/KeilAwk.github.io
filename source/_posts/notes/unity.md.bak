---
title: Unity开发
date: 2024-09
note: true
tags:
---

## BepInEX框架

## BepInEX项目配置

## BepInEX使用外部资源

在Editor内使用unity官方的Assetbundle Browser生成ab包，loadfromfile导入游戏即可

可用Paths类获取插件所在路径

## BepInEX与Unity Editor协作

在Editor内使用bepinex插件内的MonoBehaviour

直接在Editor里写空操作（只包含变量和方法的定义）MonoBehaviour组件在实际载入游戏时只有原版游戏的MonoBehaviour会被target，插件的则会因为找不到而不挂载

将插件dll添加到unity中并在inspector关闭自动引用和可用性检测即可

或者extren代码

对于游戏原版的Assembly-CSharp，同，可用dsSpy修改dll名

## HarmonyX

```csharp
var harmony = new Harmony("patch");

Class {}

[HarmonyPatch]
class Class_Patch {}

//为所有Patch创建补丁实例，包括非本插件的
harmony.PatchAll();

//仅本dll
harmony.PatchAll( Assembly.GetAssembly( typeof(Class_Patch) ) );

//指定单独Patch
CreateAndPatchAll( typeof(Class_Patch) );

//unpatch一个类的prefix
harmony.Unpatch( typeof(Class).GetMethob("methob"), HarmonyPatch.Perfix );
```

## BepInEX

## Unity

```csharp
//创建一个dontdestoryobj
DontDestoryObject( gameObject );

//创建一个static的class (下面成员必须static)
public static class Class{}

//`Awake()` 在 `Start()` 执行之前
```




