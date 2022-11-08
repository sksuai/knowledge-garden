- 操作系统建议macOS 12，不过需要注意的是内存越大越好，在16G RAM的 M1 pro MacBook上出现了内存不足的情况，此时会有较为明显的性能损失。8G RAM理论上可以跑，没做过测试。
- ![](https://kevin-roamedit.oss-cn-shenzhen.aliyuncs.com/20221108150119.png)
- 准备工作：
- Mac系统的电脑一台、内存越大越好、系统版本建议MacOS 12以上
- 可全局访问Github等国际性的网站，且网速和网络稳定性保持在你能接受的范围，如果只有几十KiB/s还动不动就断连，那请尽早放弃。
- 提前下载预训练模型文件，链接如下：
- magnet:?xt=urn:btih:3a4a612d75ed088ea542acac52f9f45987488d1c&dn=sd-v1-4.ckpt&tr=udp%3a%2f%2ftracker.openbittorrent.com%3a6969%2fannounce&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337
- 检查是否已经安装过其他版本的Python：
- 打开你的Terminal（不会打开？CMD+空格键，输入terminal就开了）
- ![](https://kevin-roamedit.oss-cn-shenzhen.aliyuncs.com/20221108150157.png)
- 输入：
- ```
  open /Library/Frameworks
  
  ```
- 如果看到有Python开头的文件夹，删掉它
- 输入：
- ```
  open /usr/local/bin 
  ```
- 如果看到有Python开头的文件或文件夹，删掉它
- 输入：
- ```
  brew cleanup
  ```
- # 安装开始
- 安装Home brew：
- 继续在你的Terminal里面输入：
- ```
  -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```
- 确认HomeBrew安装完毕后，继续在Terminal里安装需要用到的其他软件，输入：
- ```
  brew install cmake protobuf rust python git wget
  ```
- 新建一个文件夹，文件名随便取，这将是你存放Novel AI软件的地方，我们这里以：
- 桌面上“NovelAI”文件夹为例
- 安装Stable-Diffusion-WebUI，继续回到Terminal当中，按顺序输入以下命令（上一条执行完了再输入下一条：
- ```
  cd ~/Desktop/NovelAI/
  curl https://raw.githubusercontent.com/dylancl/stable-diffusion-webui-mps/master/setup_mac.sh -o setup_mac.sh  
  chmod +x setup_mac.sh
  ./setup_mac.sh
  ```
- 此时会开始自动安装，当看到询问你“是否已经下载好模型”的时候（看不懂英文的，就是第一次出现“(y),n”的时候），别急着输入，打开桌面上NovelAI文件夹，进入到stable-diffusion-webui\models\Stable-diffusion里面，将准备工作中我们下载好的“sd-v1-4.ckpt”文件拷贝到这里
- 回到Terminal界面，输入y，回车，然后一路y，回车下去；
- 如果一切顺利，最终你会看到下面的界面
- 安装成功
- ![](https://kevin-roamedit.oss-cn-shenzhen.aliyuncs.com/20221108150225.png)
- 打开Safari浏览器，输入：http://127.0.0.1:7860就可以使用了
- 关闭浏览器并不会让你的程序关闭，要在终端（Terminal）中按Control+C键；
- 以后想要运行，打开Terminal，输入：
- ```
  cd ~/Desktop/NovelAI/stable-diffusion-webui
  ./run_webui_mac.sh
  ```
- # 除BUG和其他
- 如果安装完毕的首次运行过程中出现报错等情况，大概率是依赖没装完导致的，在miniconda里按照以下步骤重装依赖：
- 1、关闭、等待一段时间、重新打开你的Terminal，或者保险起见，重启电脑
- 2、在Terminal中按顺序输入：
- ```
  cd ~/Desktop/NovelAI/stable-diffusion-webui
  conda env config vars set
  PYTORCH_ENABLE_MPS_FALLBACK=1  
  conda activate web-ui
  pip install -r requirements.txt
  ```
- 3、等待它安装完成，如果报错且没有能力排查，可以再运行一遍
- ```
  pip install -r requirements.txt
  ```
- 或者寻求谷歌大神的帮助。
- 这里顺便给一个模型库，里面有各种奇奇怪怪的模型，按需要自取：
- https://rentry.org/sdmodels
- 如果想要输出的内容与Novel AI官网差不多，需要下载和使用它们的训练结果，链接见下：
- magnet:?xt=urn:btih:5bde442da86265b670a3e5ea3163afad2c6f8ecc
- # 额外注意事项：
	- >Mac并未提供完整支持，Sampling
	  method当中必须选择Euler和DPM2开头的选项，其他选项会导致出现纯黑的色块。Upscaling必须选择real-ESRGAN类型的模型。
- 如果内存比较小，比如8G，可以考虑降低分辨率，之后再用缩放软件拉伸。
- 如果执行到 第4步，出现第5步里 y/n 的时候，并没有 stable-diffusion-webui\models\Stable-diffusion 这个目录，第5步第一次出现 y/n 的时候是提示你要安装stable-diffusion-webui 等模块, 输入 y 即可安装那些模块, 然后才会提示 Have you already installed the model? (y/n) 这个时候就会有stable-diffusion-webui\models\Stable-diffusion 这个目录了, 亲测有效。
- 性能方面，16G内存的Macbook出现了内存容量瓶颈，512x512尺寸的图片生成时间是1分40秒，GPU跑不满。缩小图片尺寸后，320x512尺寸的图片只要22秒。
- 把run_webui_mac.sh里的run webui下面那行改成
- ```
  python webui.py --precision full --lowvram --no-half --use-cpu GFPGAN CodeFormer BSRGAN ESRGAN SCUNet $@
  ```
- 可以显著减少内存占用，但是会拖慢生成速度。