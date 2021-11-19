---
title: "BLWL[7] Manjaro KDE 画面撕裂问题解决方案" 
date: 2020-01-23T22:29:58+08:00
categories: ["Better Life With Linux"]
tags: ["Manjaro", "Linux"]
draft: false
---
就如在 [BLWL02](http://jonathanwayy.xyz/2020/blwl2/) 中所提到的，之前在新机子上装 Manjaro KDE 屡试未果，画面一直撕裂，最后没办法换了 XFCE  
XFCE 倒确实顺风顺水没出什么幺蛾子，但是用习惯了 KDE 的华丽画风导致 XFCE 的扁平化风格怎么看怎么别扭  
所以再次回过头尝试 KDE  
最终确实解决了问题  
在进入U盘驱动以后，先

	sudo vi /lib/calamares/modules/mhwdcfg/main.py

修改此文件最后一行  

	def run():
	""" Configure the hardware """
	
		mhwd = MhwdController()

		# return mhwd.run()
		return None	# 把上一行注释掉，加上这一行

然后点击 **Launch Installer** 开始安装  
安装完成重启后进入系统，发现问题已经解决   
独显真是双刃剑  
可能机子不一样碰到的问题也不一样，祝大家成功排错早日用上 Manjaro  
