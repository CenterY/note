xcode 

1. edit all in scope

		Cmd-Ctrl-E to edit all in scope
		
2. Scheme的option中将Background Fetch打上勾。从这个Scheme来运行应用的时候，应用将不会直接启动切入前台，而是调用后台获取部分代码并更新UI，这样再点击图标进入应用时，你应该可以看到最新的数据和更新好的UI了

3. 环境变量 在Xcode中点击Edit Scheme，添加如下两个环境变量（可以在执行load方法以及加载category的时候打印log信息，更多的环境变量选项可参见objc-private.h）:
