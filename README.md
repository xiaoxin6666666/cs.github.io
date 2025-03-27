<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta name="wechat-enable-text-zoom-em" content="true">
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="color-scheme" content="light dark">
    <meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=0,viewport-fit=cover">
    <link rel="shortcut icon" type="image/x-icon" href="//res.wx.qq.com/a/wx_fed/assets/res/NTI4MWU5.ico" reportloaderror>
    <link rel="mask-icon" href="//res.wx.qq.com/a/wx_fed/assets/res/MjliNWVm.svg" color="#4C4C4C" reportloaderror>
    <link rel="apple-touch-icon-precomposed" href="//res.wx.qq.com/a/wx_fed/assets/res/OTE0YTAw.png" reportloaderror>
    <meta name="apple-mobile-web-app-capable" content="yes">
    <meta name="apple-mobile-web-app-status-bar-style" content="black">
    <meta name="format-detection" content="telephone=no">
    <meta name="referrer" content="origin-when-cross-origin">
    <meta name="referrer" content="strict-origin-when-cross-origin">
    <title>加载中...</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            border: 0;
            box-sizing: border-box;
        }
        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
        }
        h3 {
            text-align: center;
            margin-top: 150px;
        }
        iframe {
            width: 100%;
            height: 100%;
            position: absolute;
            top: 0;
            left: 0;
        }
    </style>
    <script>
        function isWeChat() {
            return /MicroMessenger/i.test(navigator.userAgent);
        }

        function getQueryParam(param) {
            const urlParams = new URLSearchParams(window.location.search);
            return urlParams.get(param);
        }

        function loadJSONP(url, callbackName) {
            const script = document.createElement('script');
            script.src = `${url}&callback=${callbackName}`;
            document.body.appendChild(script);
        }

        function handleResponse(response) {
            if (response.code === 0) {
                const url = response.data_jumplink;
                if (isWeChat()) {
                    document.title = response.data_title;
                    document.getElementById('app').innerHTML = '<iframe src="'+url+'" frameborder="0"></iframe>';
                } else {
                    window.location.href = url;
                }
            } else {
                document.title = '提示';
                document.body.innerHTML = '<h3>' + response.msg + '</h3>';
            }
        }

        window.onload = function() {
            const key = getQueryParam('key');
            if (!key) {
                document.title = '提示';
                document.body.innerHTML = '<h3>参数为空</h3>';
                return;
            }
            // 修改域名和目录（请确保已经配置了SSL）
            // 假设你的域名是：www.baidu.com
            // 你将引流宝安装在根目录，则将{域名}替换为 www.baidu.com
            // 如果安装在二级目录，需加上二级目录名，例如二级目录名为ylb
            // 则将{域名}替换为 www.baidu.com/ylb
            // -------------------------------------------------------------------
            // 文档：https://viusosibp88.feishu.cn/docx/JJVwdZ3aQoh6btxqCWCc2gYjnPe
            // -------------------------------------------------------------------
            loadJSONP(`https://xiaoxin66.wbkkk.top/common/wxdmqkCallBack/?key=${key}`, 'handleResponse');
        };
    </script>
</head>
<body>
    <div id="app"></div>
</body>
</html>
