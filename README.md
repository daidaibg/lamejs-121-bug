# Dealing with official 1.2.1 bug issues
Dealing with official 1.2.1 bug issues. If you want to use version 1.2.1, you can use this package without making any modifications
处理官方1.2.1bug问题 如果要使用1.2.1版本可以使用这个包不用做任何修改
# lamejs
Fast mp3 encoder written in JavaScript.
On my machine it works 20x faster than realtime (it will encode 132 second long sample in 6.5 seconds) both on node and chrome.
lamejs is a rewrite of jump3r-code which is a rewrite of libmp3lame.

## “ReferenceError: MPEGMode is not defined”

“ReferenceError: MPEGMode is not defined”
MPEGMode is not defined at lame_init_old (Lame.js?dead:135:1) at Lame.lame_init
这个是旧的版本自带的bug
解决办法找到node_modules/lamejs文件夹修改下面的文件
Lame.js:29行 Encoder.js:112 行 PsyModel.js:162行 添加 var MPEGMode = require(‘./MPEGMode.js’);

BitStream.js:33行 Presets.js:18行 添加 var Lame = require(‘./Lame.js’);

QuantizePVT.js:54行 添加var BitStream = require(‘./BitStream.js’);

### 官方文档
[https://github.com/zhuker/lamejs#readme]](https://github.com/zhuker/lamejs#readme)
