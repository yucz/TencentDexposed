# TencentDexposed
腾讯HOOK框架, 支持xposed接口

```
com.tencent.qapmsdk.Magnifier.sApp = this.getApplication();
        if (!com.tencent.qapmsdk.io.util.NativeMethodHook.hooksoLoadSign) {
            System.loadLibrary("apmioFake");
            System.loadLibrary("apmart");
            com.tencent.qapmsdk.io.util.NativeMethodHook.iosoLoadSign = true;
            com.tencent.qapmsdk.io.util.NativeMethodHook.hooksoLoadSign = true;
        }
        com.tencent.qapmsdk.io.dexposed.DexposedBridge.findAndHookMethod(Application.class,
                "onCreate", new com.tencent.qapmsdk.io.dexposed.XC_MethodHook() {
                    @Override
                    public void afterHookedMethod(com.tencent.qapmsdk.io.dexposed.XC_MethodHook.MethodHookParam param) {
                        super.beforeHookedMethod(param);
                        param.setResult(null);
                    }
                });
```
