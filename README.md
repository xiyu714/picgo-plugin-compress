## picgo-plugin-compress

[![build](https://img.shields.io/github/workflow/status/juzisang/picgo-plugin-compress/NPMPublish/master?color=brightgreen)](https://github.com/JuZiSang/picgo-plugin-compress/actions)
[![dm](https://img.shields.io/npm/dm/picgo-plugin-compress?color=brightgreen)](https://npmcharts.com/compare/picgo-plugin-compress?minimal=true)
[![v](https://img.shields.io/npm/v/picgo-plugin-compress?color=brightgreen)](https://www.npmjs.com/package/picgo-plugin-compress)
[![mit](https://img.shields.io/badge/license-mit-brightgreen.svg)](https://github.com/JuZiSang/picgo-plugin-compress/blob/master/LICENSE)

用于 [PicGo](https://github.com/Molunerfinn/PicGo) 的图片压缩插件,支持 [TinyPng](https://tinypng.com/) [ImageMin](https://github.com/imagemin/imagemin)

## 安装

### [PicGo-Core](https://github.com/PicGo/PicGo-Core) 安装

- 安装 `picgo add compress`

- 选择使用 `picgo use transformer`

- 参数配置 `picgo config plugin compress`

  compress 选择压缩工具
  默认选项

  - [imagemin](https://github.com/imagemin/imagemin) +luban 算法，最大程度节省流量，默认选项
  - [imagemin](https://github.com/imagemin/imagemin) 压缩过程不需要经过网络，但是图片会有损耗
  - imagemin_webp 本地有损压缩，支持GIF格式有损压缩
    注意：有些图床（比如sm.ms）不支持webp图片格式，会上传失败
  - [tinypng](https://tinypng.com/) 无损压缩，需要上传到 tinypng
  - lubanforgitee  将所有图片压缩到1M以下,解决gitee的1M外链不能访问的问题. 

nameType 是否重命名

  - timestamp 重命名成时间戳
- none 不重名，默认选项
  

key 可选

  - 在 [developers](https://tinypng.com/developers) 中申请
  - 逗号`,`隔开，可使用多个 Key 叠加使用次数

### [PicGo-Gui](https://github.com/Molunerfinn/PicGo) 在线安装

- 打开详细窗口 > 插件设置 > 搜索 `compress` 即可安装，配置同上
- 离线安装参考[这里](https://picgo.github.io/PicGo-Core-Doc/zh/dev-guide/deploy.html#gui%E6%8F%92%E4%BB%B6)

## 压缩效果对比

| 类型   | tinypng                                                      | luban                                                        | imagemin                                                     | imagemin_webp                                                |
| ------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 原大小 | 1.5 MB                                                       | 1.5 MB                                                       | 1.5 MB                                                       | 1.5 MB                                                       |
| 压缩后 | 315 KB                                                       | 276 KB                                                       | 411 KB                                                       | 216 KB                                                       |
| 效果图 | ![](https://raw.githubusercontent.com/JuZiSang/picgo-plugin-compress/master/tests/tinypng.png) | ![](https://raw.githubusercontent.com/JuZiSang/picgo-plugin-compress/master/tests/luban.png) | ![](https://raw.githubusercontent.com/JuZiSang/picgo-plugin-compress/master/tests/imagemin.png) | ![](https://raw.githubusercontent.com/JuZiSang/picgo-plugin-compress/master/tests/imagemin_webp.webp) |
