# EasyCommon [![](https://jitpack.io/v/LimeVista/EasyCommon.svg)](https://jitpack.io/#LimeVista/EasyCommon)
An Android Common Component（一个用于Android快速开发小工具集合）

## How to
* To get a Git project into your build:
* Step 1. Add the JitPack repository to your build file
```groovy
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```

* Step 2. Add the dependency
```groovy
 compile 'com.github.LimeVista:EasyCommon:0.1.2'
```

* Step 3.CompileOptions
```groovy
android {
    ...
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
``` 
## Method
* AppManager: Application Manager(应用管理) => [AppManager.kt](https://github.com/LimeVista/EasyCommon/blob/master/common/src/main/java/me/limeice/common/base/app/AppManager.kt).
```kotlin
    fun finishActivity()                        // 结束当前Activity

    fun addActivity(activity: Activity)         // 添加Activity

    fun currentActivity(): Activity?            // 获取当前Activity

    fun finishActivity(activity: Activity)      // 结束指定Activity

    fun removeActivity(activity: Activity)      // 移除指定的Activity

    fun <T> returnToActivity(clazz: Class<T>    // 返回到指定的Activity

    fun <T> isOpenActivity(clazz: Class<T>)     //是否已经打开指定的activity

    fun appExit(isBackground: Boolean)          // Exit Application, 退出应用程序

    fun Activity.finishCurrent()                // 结束当前Activity
```
* BytesUtils: Bytes Utils(字节流处理工具) => [BytesUtils.java](https://github.com/LimeVista/EasyCommon/blob/master/common/src/main/java/me/limeice/common/function/BytesUtils.java).
```java
    /**
     * Convert byte array to hex string => 将字节数组转换为16进制字符串
     *
     * @param bytes byte array, eg:[0x1A,0x2C,0x3B] => 输入 [0x1A,0x2C,0x3B]
     * @return hex string, eg: 1A2C3B => 得到 1A2C3B
     */
    @NonNull
    public static String toHexString(@NonNull byte[] bytes) 

    /**
     * Convert byte to hex value => 将字节转换为16进制表示
     *
     * @param b byte, eg: 8 => 输入 8 
     * @return hex value, eg: 0x08 => 得到 0x08
     */
    @NonNull
    public static String convert(byte b) 

    /**
     * Convert byte array to hex values => 将字节数组转换为16进制字符串表示
     *
     * @param bytes byte array, eg: [8,1] => 输入 [8,1]
     * @return hex value, eg: [0x08, 0x01] => 得到(包含中括号) [0x08, 0x01]
     */
    @NonNull
    public static String convert(@NonNull final byte[] bytes) 

    /**
     * Convert hex string to byte array=> 将16进制字符串转换为字节数组
     *
     * @param hexString hex string eg: 1A2C3B => 输入 1A2C3B
     * @return byte array eg: [0x1A,0x2C,0x3B] =>得到 [0x1A,0x2C,0x3B]
     */
    @Nullable
    public static byte[] hexStringToBytes(@Nullable String hexString)
```
* CloseUtils: Close Stream Utils(关闭流处理工具) => [CloseUtils.java](https://github.com/LimeVista/EasyCommon/blob/master/common/src/main/java/me/limeice/common/function/CloseUtils.java).
```java
    /**
     * 关闭IO
     *
     * @param closeables closeables
     */
    public static void closeIO(final Closeable... closeables)

    /**
     * 关闭IO(静默操作)
     *
     * @param closeables closeables
     */
    public static void closeIOQuietly(final Closeable... closeables) 

    /**
     * 关闭IO(静默操作)
     *
     * @param closeable closeable
     */
    public static void closeIOQuietly(final Closeable closeable)
```
* ColorUtils: Color Utils(颜色处理工具) => [ColorUtils.java](https://github.com/LimeVista/EasyCommon/blob/master/common/src/main/java/me/limeice/common/function/ColorUtils.java).
```java
    /**
     * 根据Attribute属性的资源ID值，获取颜色值
     *
     * @param context Context容器
     * @param attr    属性ID
     * @return 颜色值
     */
    public static int getAttrColor(@NonNull Context context, @AttrRes int attr)

    /**
     * 根据Resources的Color id值生成ColorDrawable
     *
     * @param context Context容器
     * @param id      res中颜色的id值
     * @return ColorDrawable画布
     */
    @NonNull
    public static ColorDrawable getColorDrawable(@NonNull Context context, @ColorRes int id) 

    /**
     * 从ColorInt提取颜色值，色值0~255
     *
     * @param color 颜色值
     * @return 数组长度为4, <code> array[0] = A; array[1] = R; array[2] = G; array[3] = B </code>
     */
    @NonNull
    public static byte[] getARGB(@ColorInt int color)

    /**
     * 从ColorInt提取颜色值，色值0~255
     *
     * @param color 颜色值
     * @return 数组长度为3, array[0] = R; array[1] = G; array[2] = B </code>
     */
    @NonNull
    public static byte[] getRGB(@ColorInt int color) 
```
* IOUtils: Input Output Utils(输入输出及文件处理工具) => [IOUtils.java](https://github.com/LimeVista/EasyCommon/blob/master/common/src/main/java/me/limeice/common/function/IOUtils.java).
```java
     /**
     * 从输入流中读取数据，并转换为Byte数组
     *
     * @param inStream 待操作的输入流
     * @return Byte数组形式的html文件
     * @throws IOException 各种异常，包括IOException
     */
    @NonNull
    public static byte[] read(@NonNull InputStream inStream) 

    /**
     * 从输入流中读取数据，并转换为Byte数组
     *
     * @param file 文件
     * @return Byte数组形式的html文件
     * @throws IOException IOException
     */
    @NonNull
    public static byte[] read(@NonNull File file)

    /**
     * 从输入流中读取数据，并转换为Byte数组
     *
     * @param filePath 文件路径
     * @return Byte数组形式的html文件
     * @throws IOException IOException
     */
    @NonNull
    public static byte[] read(@NonNull String filePath) throws IOException {
        return read(new File(filePath));
    }


    /**
     * 写入数据
     *
     * @param filePath 文件路径（如果存在覆盖，否则创建）
     * @param msg      文本（被写入数据）
     * @throws IOException IOException
     */
    public static void write(@NonNull String filePath, @NonNull String msg) 

    /**
     * 写入数据
     *
     * @param filePath 文件路径（如果存在覆盖，否则创建）
     * @param bytes    字节数据（被写入数据）
     * @throws IOException IOException
     */
    public static void write(@NonNull String filePath, @NonNull byte[] bytes) 

    /**
     * 写入数据
     *
     * @param file 文件（如果存在覆盖，否则创建）
     * @param msg  文本（被写入数据）
     * @throws IOException IOException
     */
    public static void write(@NonNull File file, @NonNull String msg)

    /**
     * 写入数据
     *
     * @param file  文件（如果存在覆盖，否则创建）
     * @param bytes 字节数据（被写入数据）
     * @throws IOException IOException
     */
    public static void write(@NonNull File file, @NonNull byte[] bytes) 

    /**
     * 写入数据
     *
     * @param file  文件（如果存在追加，否则创建）
     * @param bytes 字节数据（被写入数据）
     * @throws IOException IOException
     */
    public static void writeAppend(@NonNull File file, @NonNull byte[] bytes)
    /**
     * 写入数据
     *
     * @param file   文件（如果存在覆盖，否则创建）
     * @param bytes  字节数据（被写入数据）
     * @param offset 偏移量
     * @param len    写入长度
     * @throws IOException IOException
     */
    public static void write(@NonNull File file, @NonNull byte[] bytes, int offset, int len) 

    /**
     * 检查文件是否存在，否则创建
     *
     * @param file 文件
     * @throws IOException IOException
     */
    public static void checkFileIfNotExistCreate(File file)

    /**
     * 压缩文件
     *
     * @param input  输入流（源文件）
     * @param output 输出流（压缩文件）
     * @throws IOException IOE
     */
    public static void zip(@NonNull InputStream input, @NonNull OutputStream output)

    /**
     * 解压文件
     *
     * @param input  输入流(压缩文件)
     * @param output 输出流（源文件）
     * @throws IOException IOE
     */
    public static void unzip(@NonNull InputStream input, @NonNull OutputStream output)

    /**
     * 文件复制
     *
     * @param input  输入文件（被复制文件）
     * @param output 输出文件（复制文件）
     * @return 是否复制成功
     */
    public static boolean copyFile(@Nullable File input, @Nullable File output)

    /**
     * 移动文件
     *
     * @param input  输入文件
     * @param output 输出文件
     * @return 是否移动成功{@code true}成功否则失败
     */
    public static boolean moveFile(@Nullable File input, @Nullable File output)
```
* DensityUtils: Density Utils(屏幕分辨率处理工具) => [DensityUtils.java](https://github.com/LimeVista/EasyCommon/blob/master/common/src/main/java/me/limeice/common/function/DensityUtils.java).
```java
 /**
     * 根据手机的分辨率从 dp 值 转成为 px(像素)值
     *
     * @param context 被转换值的所在Context容器
     * @param dpValue dp值
     * @return px(像素)值
     */
    public static int dip2px(Context context, float dpValue) 

    /**
     * 根据手机的分辨率从 px(像素)值 转成为 dp 值
     *
     * @param context 被转换值的所在Context容器
     * @param pxValue px(像素)值
     * @return dp值
     */
    public static int px2dip(Context context, float pxValue)

    /**
     * 根据手机分辨率，将 px 值转换为 sp 值，保证文字大小不变
     *
     * @param pxValue px(像素)值
     * @return sp值
     */
    public static int px2sp(Context context, float pxValue)
    /**
     * 根据手机分辨率，将 sp 值转换为 px 值，保证文字大小不变
     *
     * @param spValue sp值
     * @return px(像素)值
     */
    public static int sp2px(Context context, float spValue) 

    /**
     * 获取屏幕宽度
     *
     * @param context 被转换值的所在Context容器
     * @return (px像素)屏幕宽度
     */
    public static int getScreenWidth(Context context)

    /**
     * 获取屏幕高度
     *
     * @param context 被转换值的所在Context容器
     * @return (px像素)屏幕高度
     */
    public static int getScreenHeight(Context context)

    /**
     * 获取状态栏高度
     *
     * @param context 被转换值的所在Context容器
     * @return 状态栏高度
     */
    public static int getStatusBarHeight(Context context)

    /**
     * 获取虚拟功能键高度
     */
    public static int getVirtualBarHeight(Context context)

    /**
     * 获取屏幕真实高度
     * Android 4.2开始才有的API，在这之前可能无效
     *
     * @param context 上下文容器
     * @return 屏幕高度
     */
    public static int getScreenRealHeight(Context context) 
```
* DeepClone: Deep Clone Utils(深度复制工具) => [DeepClone.java](https://github.com/LimeVista/EasyCommon/blob/master/common/src/main/java/me/limeice/common/function/DeepClone.java).
```java
   /**
     * Deep clone => 深度复制
     *
     * @param obj a Object extends Serializable => 被克隆对象
     * @param <T> Object Type          => 输入类泛型
     * @return copy of the object      => 复制对象
     * @throws IOException            IOException
     * @throws ClassNotFoundException ClassNotFoundException
     */
    public static <T extends Serializable> T deepClone(T obj) 

    /**
     * serialize a object => 序列化对象
     *
     * @param file save file path   => 保存文件
     * @param obj  object           => 被序列化对象
     * @param <T>  extends Serializable
     */
    public static <T extends Serializable> void serialize(@Nullable File file, @Nullable T obj) 

    /**
     * deserialize a Object => 反序列化对象
     *
     * @param file file         => 获取文件
     * @param <T>  Object Class => 类泛型
     * @return Object           => 实例化对象
     */
    @Nullable
    public static <T extends Serializable> T deserialize(@NonNull File file) 
```