<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
    <title>链接检测中</title>
    <style>/* 保持原有样式不变 */</style>
</head>
<body>
    <div class="container">
        <img src="https://anrx87.neocities.org/%E5%B7%A5%E5%85%B7/c36c34744e2f4f65a5e9d3da05ba37df.gif" class="custom-gif" alt="加载中">
        <h2 class="title">正在准备访问</h2>
        <p id="status" class="status checking">正在检查可用链接...</p>
        <p class="tip">若长时间无响应，请检查网络</p>
        <button class="clear-cache" onclick="localStorage.removeItem('lastWorkingUrl')">清除缓存，重新检测</button>
    </div>

    <script>
        const targetUrls = [
            "https://yc.hk11w.cn/m/index",
            "https://yc.chenyutongxin.com/m/index", 
            "https://yc.10099hk.cn/m/index"
        ];
        const cacheKey = "lastWorkingUrl";
        const checkTimeout = 10000;
        const statusEl = document.getElementById("status");
        const gifEl = document.querySelector(".custom-gif");

        window.onload = function() {
            const cachedUrl = localStorage.getItem(cacheKey);
            if (cachedUrl) {
                window.location.href = cachedUrl;
                return;
            }
            checkUrlsInOrder(0);
        };

        function checkUrlsInOrder(index) {
            if (index >= targetUrls.length) {
                gifEl.style.display = "none";
                statusEl.textContent = "所有链接均无法访问，请稍后再试";
                statusEl.className = "status error";
                return;
            }

            const currentUrl = targetUrls[index];
            statusEl.textContent = `正在检测第${index + 1}个链接: ${currentUrl}`;
            statusEl.className = "status checking";

            // 模拟浏览器的请求头（关键！）
            const headers = new Headers();
            headers.append("User-Agent", "Mozilla/5.0 (Linux; Android 10; Redmi K30) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.91 Mobile Safari/537.36");
            headers.append("Referer", currentUrl); //  Referer设为自身网址，模拟同域访问

            const controller = new AbortController();
            const timeoutTimer = setTimeout(() => {
                controller.abort();
                statusEl.textContent = `第${index + 1}个链接超时，尝试下一个...`;
                setTimeout(() => checkUrlsInOrder(index + 1), 800);
            }, checkTimeout);

            fetch(currentUrl, {
                method: "GET", // 改成GET请求，更贴近浏览器访问逻辑
                signal: controller.signal,
                mode: "cors",
                cache: "no-store",
                headers: headers // 注入模拟的请求头
            })
            .then(() => {
                clearTimeout(timeoutTimer);
                statusEl.textContent = `第${index + 1}个链接可用，正在跳转...`;
                statusEl.className = "status success";
                localStorage.setItem(cacheKey, currentUrl);
                setTimeout(() => window.location.href = currentUrl, 1000);
            })
            .catch(() => {
                clearTimeout(timeoutTimer);
                statusEl.textContent = `第${index + 1}个链接不可用，尝试下一个...`;
                statusEl.className = "status error";
                setTimeout(() => checkUrlsInOrder(index + 1), 800);
            });
        }
    </script>
</body>
</html>
