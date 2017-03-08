### MAC 快捷键
1. 移动文件

		command + c
		option + command + v
		
2. 打开文件夹

		command + o
		
3. 显示隐藏文件/恢复文件隐藏

		 shift+command+.
		 
4. 查看文件夹及子文件夹占用空间

		du -sh *
		
5. 维护脚本可定期执行

		sudo periodic daily weekly monthly
		
6. 截屏（默认存放在桌面可修改截图类型）

		shift+command+3 // 全屏
		shift+command+4 // 鼠标选取部分
		defaults write com.apple.screencapture type -string JPEG // 修改保存图片类型
		
7. 批量复制文件

		cp *.png *.gif /destpath // 复制同一文件夹下指定类型文件到/destpath
		
8. 远程复制文件

		scp ./testfile.txt username@ip:/tmp // 回车输入username的密码 会把当前目录下的testfile.txt 复制到远程机器的tmp目录下
		scp username@ip:/tmp/testfile.txt ./ // 从远程机器复制到本地
		
9. 查看历史命令

		history  // 列出历史命令加编号
		histpory | grep pod 根据关键字pod找历史命令
		!101 // 根据编号执行历史命令
10. 便签

		复制文字 shift + command + y
		
11. 保持当前层级移动窗口

		按住command 拖拽窗口
		
12. Safari 

		按住command 点击链接，在新标签页打开
		shift + command + 左右方向键可在Safari标签页间切换
13. 同组程序切换
        
        command+`(esc下面的键)
