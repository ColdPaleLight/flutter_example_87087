click "start activity and trigger crash"
you will see the native crash with log:
```
*** *** *** *** *** *** *** *** *** *** *** *** *** *** *** ***
Build fingerprint: 'HUAWEI/ELS-AN00/HWELS:10/HUAWEIELS-AN00/102.0.0.138C00:user/release-keys'
Revision: '0'
ABI: 'arm64'
SYSVMTYPE: Maple
APPVMTYPE: Art
Timestamp: 2021-08-06 21:16:20+0800
pid: 19432, tid: 21446, name: 1.raster  >>> com.example.surface_texture_demo_example <<<
uid: 10504
signal 11 (SIGSEGV), code 1 (SEGV_MAPERR), fault addr 0x660
Cause: null pointer dereference
    x0  0000000000000660  x1  0000006fd617d9d4  x2  000000006f91d72c  x3  0000006fac45b000
    x4  0000006fd617dfa0  x5  000000704ab71a46  x6  0000000000000000  x7  0000000000000001
    x8  0000000000000000  x9  c45dfd17366734bc  x10 0000000000430000  x11 000000704bbe0000
    x12 000000704b723224  x13 000000704b72326c  x14 000000704b7232cc  x15 0000000000000000
    x16 00000070cd9ab458  x17 00000070cf31e190  x18 0000006fd3652000  x19 0000000000000000
    x20 0000000000000660  x21 0000006fac45b000  x22 00000070cc7e50a0  x23 00000070cc7e2028
    x24 0000000000000004  x25 0000006fd617f020  x26 0000006fac45b0b0  x27 0000000000000001
    x28 0000000000000003  x29 0000006fd617d980
    sp  0000006fd617d950  lr  00000070cd49dcf4  pc  00000070cf31e190
backtrace:
      #00 pc 00000000000d0190  /apex/com.android.runtime/lib64/bionic/libc.so (pthread_mutex_lock) (BuildId: e0a2a32acc18e871df44c7f6f8c912df)
      #01 pc 00000000001c1cf0  /system/lib64/libhwui.so (android::SurfaceTexture::detachFromContext()+108) (BuildId: 9989057d37fad036d953944e77aba368)
      #02 pc 00000000001c47b4  /system/lib64/libandroid_runtime.so (android::SurfaceTexture_detachFromGLContext(_JNIEnv*, _jobject*)+80) (BuildId: 7b48cf6bb60e638a9b70eb007535bff3)
      #03 pc 00000000002e2dac  /system/framework/arm64/boot-framework.oat (art_jni_trampoline+124) (BuildId: 85db6f9895bf447b3f668e6cd98ce4ac26674d53)
      #04 pc 0000000000146334  /apex/com.android.runtime/lib64/libart.so (art_quick_invoke_stub+548) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #05 pc 00000000001551b4  /apex/com.android.runtime/lib64/libart.so (art::ArtMethod::Invoke(art::Thread*, unsigned int*, unsigned int, art::JValue*, char const*)+252) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #06 pc 00000000002fbfec  /apex/com.android.runtime/lib64/libart.so (art::interpreter::ArtInterpreterToCompiledCodeBridge(art::Thread*, art::ArtMethod*, art::ShadowFrame*, unsigned short, art::JValue*)+384) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #07 pc 00000000002f72bc  /apex/com.android.runtime/lib64/libart.so (bool art::interpreter::DoCall<false, false>(art::ArtMethod*, art::Thread*, art::ShadowFrame&, art::Instruction const*, unsigned short, art::JValue*)+912) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #08 pc 00000000005cbfe8  /apex/com.android.runtime/lib64/libart.so (MterpInvokeDirect+400) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #09 pc 0000000000140914  /apex/com.android.runtime/lib64/libart.so (mterp_op_invoke_direct+20) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #10 pc 00000000003c79e8  /system/framework/framework.jar (android.graphics.SurfaceTexture.detachFromGLContext)
      #11 pc 00000000005c9f4c  /apex/com.android.runtime/lib64/libart.so (MterpInvokeVirtual+1432) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #12 pc 0000000000140814  /apex/com.android.runtime/lib64/libart.so (mterp_op_invoke_virtual+20) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #13 pc 00000000000b430c  [anon:dalvik-classes.dex extracted in memory from /data/app/com.example.surface_texture_demo_example-1UD4QFeBEAqStUde0xEbJQ==/base.apk] (io.flutter.embedding.engine.renderer.SurfaceTextureWrapper.detachFromGLContext+4)
      #14 pc 00000000002cc918  /apex/com.android.runtime/lib64/libart.so (_ZN3art11interpreterL7ExecuteEPNS_6ThreadERKNS_20CodeItemDataAccessorERNS_11ShadowFrameENS_6JValueEbb.llvm.9717788196832654690+320) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #15 pc 00000000005ba77c  /apex/com.android.runtime/lib64/libart.so (artQuickToInterpreterBridge+1012) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #16 pc 000000000014f468  /apex/com.android.runtime/lib64/libart.so (art_quick_to_interpreter_bridge+88) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #17 pc 0000000000146334  /apex/com.android.runtime/lib64/libart.so (art_quick_invoke_stub+548) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #18 pc 00000000001551b4  /apex/com.android.runtime/lib64/libart.so (art::ArtMethod::Invoke(art::Thread*, unsigned int*, unsigned int, art::JValue*, char const*)+252) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #19 pc 00000000004d6f0c  /apex/com.android.runtime/lib64/libart.so (art::(anonymous namespace)::InvokeWithArgArray(art::ScopedObjectAccessAlreadyRunnable const&, art::ArtMethod*, art::(anonymous namespace)::ArgArray*, art::JValue*, char const*)+104) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #20 pc 00000000004d825c  /apex/com.android.runtime/lib64/libart.so (art::InvokeVirtualOrInterfaceWithVarArgs(art::ScopedObjectAccessAlreadyRunnable const&, _jobject*, _jmethodID*, std::__va_list)+424) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #21 pc 00000000003b20f0  /apex/com.android.runtime/lib64/libart.so (art::JNI::CallVoidMethodV(_JNIEnv*, _jobject*, _jmethodID*, std::__va_list)+656) (BuildId: 19bbc2cfafe97c9664d1bc891cd9abfa)
      #22 pc 000000000145d748  /data/app/com.example.surface_texture_demo_example-1UD4QFeBEAqStUde0xEbJQ==/lib/arm64/libflutter.so (BuildId: 3a357b942125657f898ffd5e99946986c597e938)
      #23 pc 0000652905364428  <unknown>
```

