- # 问题
- mac finder 中每次打开不同文件夹都要手动改成 list view 和字体大小，很烦。
  
  关于如何一次性修改所有文件夹，网上众说纷纭，试了很多都不行，头疼了一阵。
  
  想着 apple 应该不至于这么蠢，上官网搜了一下，果然有很简单的方法就可以实现。
- # 方法：
- > 1. 打开 finder，进入根目录（包含 Macintosh HD），选中 list view，然后 view->show view options 修改成你想要的样子，选中 Always open in XXX 和 Browse in XXX，然后 Use as defaults。
- > 2. 进入 Macintosh HD 目录，重复上面步骤，但不要选中 Always open in XXX 和 Browse in XXX。这样所有 Macintosh HD 中的文件夹都是同一个 view option 了。
- 我猜大概原理就是顶层目录生成一个配置文件，然后所有次级目录不用自己的配置文件，而用上一层的。
- [[Question]]：如何在任意Finder 中进入到上层文件夹？
	- 在任意文件夹 `command+🔼`。
-