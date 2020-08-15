

<!--
 * @Author       : Jingsheng Lyu
 * @Date         : 2020-08-15 12:49:42
 * @LastEditors  : Jingsheng Lyu
 * @LastEditTime : 2020-08-15 13:10:13
 * @FilePath     : /undefined/home/jingsheng/Linux_Learning/Install_Git_LFS.md
 * @Github       : https://github.com/jingshenglyu
 * @Web          : https://jingshenglyu.github.io/
 * @E-Mail       : jingshenglyu@gmail.com
-->
# Git LFS for the large files

## 1. Download [Git LFS](https://git-lfs.github.com/)

* Go to the folder of this download file and Unzip
    ```
    cd /your_PATH/
    tar -zxvf git-lfs-linux-amd64-v2.11.0.tar.gz 
    ```

## 2. Install
### From binary

* Install Git LFS binaries onto the system `$PATH`
* Run `git lfs install` to
perform required global configuration changes.

* Then using bash
    ``` 
    sudo ./install.sh
    ```

## 3. Example
### Push the large file to Github

* Track the large file
    ```
    git lfs track *.pdf
    ```
> Note: You can track the files that you want to push.(e.g. others .jpg, .mp4 und so weiter)

* Commit changes to the [.gitattributes](https://git-scm.com/docs/gitattributes) file. This can be done by running:
    ```
    git add .gitattributes
    git commit -m "track *.pdf files using Git LFS"
    ```

* Normal push:
    ```
    git add your_file.pdf
    git commit -m "push the file"
    git push origin master
    ```