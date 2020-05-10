# How to install Matlab R2020a on Ubuntu 18.04 #

### 1. 前往Mathworks，官网，下载最新版本的Matlab压缩包 ###

https://www.mathworks.com/downloads/

*点击下载后若有账号，则直接跳转到下载页面，选择下载Linux版本后，会在浏览器的下载文件夹下载一个.zip的压缩文件夹

### 2. 打开Terminal,在主目录下新建文件夹，并解压缩 ###


  $mkdir Mathworks_R2020a
  $cd Mathworks_R2020a/
  ~/Mathworks_R2020a$unzip matlab_R2020a_glnxa64.zip


### 3. 在解压后的文件夹内执行,并输入用户名密码 ###


  ~/Mathworks_R2020a$sudo ./install


### 4. 然后会弹出下载页面，输入用户名，密码后直接按指示下一步，下一步安装就好 ###

*其中有一步出现提示，Create symbolic links to MATLAB scripts in:/usr/local/bin，在该选向前打勾，表明同意在/usr/local/bin目录下创建符号连接，这样以后可以直接在终端输入matlab来打开
 
 ### 5. 完成安装 ###
 
