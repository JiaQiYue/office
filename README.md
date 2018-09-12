##插件功能，打开附件

###使用说明

###传递url打开附件

	cordova.plugins.OfficePlugin.openFileByFileUrl(success, error,fileurl,isNeedSelect)

* 参数说明

	>success 成功回调
	
	>error 失败回调

	>fileurl 此处传要打开的url
	
	>isNeedSelect 打开附件是否需要选择应用进行打开，如果使用本应用打开传false,提示选择第三方应用打开true


* 调用示例

   		<Button onclick="cordova.plugins.OfficePlugin.openFileByFileUrl(
            function(msg){
             alert(msg);
            },function(msg){
             alert(msg);
         },'https://hrsit.noahwm.com/hms-noah/interface/getHfmAttachment/?attachment_id=2812&table_name=AM_ACCOUNT_CANCEL_REQUISITION&table_pk_value=1247',true)">openFileByFileUrl</button>

	
###传递sd卡上附件的绝对路径打开附件

	cordova.plugins.OfficePlugin.openFileByFilePath(success,error,arg)

* 参数说明

	>success 成功回调
	
	>error 失败回调

	>arg 此处传要打开附件在sd卡上的绝对路径


* 调用示例

   		<Button onclick="cordova.plugins.OfficePlugin.openFileByFilePath(
            function(msg){
             alert(msg);
            },function(msg){
             alert(msg);
         },'/sdcard/关于CrossWalk插件wrapping之后的apk分析.doc')">openFileByFilePath</button>


#注:如果你的插件包含android-support-v4而且还安装了Crosswalk插件，那么编译时就会发生v4包冲突，下面是解决方案

##关于与Crosswalk android-support-v4包冲突问题解决方案

	首先你先安装Crosswalk这个插件，然后在officePlugin的plugin.xml文件中注释这行
	<source-file src="src/android/libs/android-support-v4.jar" target-dir="libs" />
	最后在plugin.xml中添加
	<dependency id="cordova-plugin-crosswalk-webview" version="2.1.0"/>
	其中id是需要依赖的插件id  version是需要依赖的插件版本

#注：如果附件部分能够打开，部分附件打开会崩溃，原因很有可能是android-support-v4包没有依赖上，因为sdk底层依赖v4包


#附  附件测试地址：
		https://hrsit.noahwm.com/hms-noah/appLogin/getAttachment?attachment_id=1170&access_id=37A6BAC7DDFB2116E05353A8040A17D8&table_name=CSH_PAYMENT_REQUISITION_HDS&table_pk_value=1433

		https://exco.noahwm.com/hec/atm_download.svc?attachment_id=26797&access_id=3ADD6FE37A605402E0531560030A38EF&table_name=CON_CONTRACT_HEADERS&table_pk_value=2954

		https://exco.noahwm.com/hec/atm_download.svc?attachment_id=21864&access_id=37A43A49CD2D760CE0531560030A6729&table_name=EXP_REPORT_HEADERS&table_pk_value=45853# office
