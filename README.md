# annieshih1217.github.io
<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<title>台灣時鐘</title>
<style>
body {
    margin: 0;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: "Microsoft JhengHei", sans-serif;
    background: linear-gradient(135deg, #1e3c72, #2a5298);
}

.clock-box {
    text-align: center;
    background: rgba(208,224,232,1);
    padding: 30px;
    border-radius: 20px;
    width: 250px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    color: #333;
}

.time {
    font-size: 48px;
    letter-spacing: 2px;
}

.date {
    font-size: 14px;
    margin-top: 8px;
    opacity: 0.8;
}

.label {
    font-size: 14px;
    margin-bottom: 5px;
    opacity: 0.7;
}
</style>
</head>
<body>

<div class="clock-box">
    <div class="label">🇹🇼 Taipei Time</div>
    <div class="time" id="time">--:--:--</div>
    <div class="date" id="date">載入中...</div>
</div>

<script>
function updateClock() {
    const now = new Date();

    const time = new Intl.DateTimeFormat("zh-TW", {
        timeZone: "Asia/Taipei",
        hour: "2-digit",
        minute: "2-digit",
        second: "2-digit",
        hour12: false
    }).format(now);

    const date = new Intl.DateTimeFormat("zh-TW", {
        timeZone: "Asia/Taipei",
        year: "numeric",
        month: "long",
        day: "numeric",
        weekday: "long"
    }).format(now);

    document.getElementById("time").innerText = time;
    document.getElementById("date").innerText = date;
}

setInterval(updateClock, 1000);
updateClock();
</script>

</body>
</html>
