<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>高知・酔いどれルートメーカー</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <style>
        body { margin: 0; font-family: sans-serif; }
        #map { height: 70vh; width: 100%; }
        .controls { padding: 15px; background: #f8f9fa; }
        .btn { background: #e63946; color: white; border: none; padding: 10px 20px; cursor: pointer; border-radius: 5px; }
        .status { margin-top: 10px; font-weight: bold; color: #1d3557; }
    </style>
</head>
<body>

<div class="controls">
    <h2>🍶 高知・はしご酒ナビ</h2>
    <label>酔い度（千鳥足レベル）: </label>
    <input type="range" id="drunkLevel" min="0" max="100" value="20">
    <button class="btn" onclick="generateRoute()">ルート生成ぜよ！</button>
    <div id="info" class="status">ひろめ市場から次のお店へ...</div>
</div>
<div id="map"></div>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script>
    // 1. 地図の初期化（高知・ひろめ市場周辺）
    const hiromePos = [33.5606, 133.5361];
    const map = L.map('map').setView(hiromePos, 17);
    
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png').addTo(map);

    // 2. スポットデータ（仮）
    const spots = [
        { name: "ひろめ市場", pos: [33.5606, 133.5361] },
        { name: "はりまや橋", pos: [33.5594, 133.5428] },
        { name: "55番街", pos: [33.5612, 133.5385] }
    ];

    spots.forEach(s => L.marker(s.pos).addTo(map).bindPopup(s.name));

    let routeLine;

    function generateRoute() {
        if (routeLine) map.removeLayer(routeLine);

        const drunk = document.getElementById('drunkLevel').value / 5000; // 酔い度
        const start = spots[0].pos;
        const end = spots[1].pos; // はりまや橋へ

        // 3. 千鳥足アルゴリズム
        // 直線を細かく分割し、ランダムなノイズ（千鳥足）を加える
        let points = [];
        const segments = 50; // 分割数

        for (let i = 0; i <= segments; i++) {
            let lat = start[0] + (end[0] - start[0]) * (i / segments);
            let lng = start[1] + (end[1] - start[1]) * (i / segments);

            // 酔い度が高いほど座標がズレる
            if (i > 0 && i < segments) {
                lat += (Math.random() - 0.5) * drunk;
                lng += (Math.random() - 0.5) * drunk;
            }
            points.push([lat, lng]);
        }

        // 4. 地図に描画
        routeLine = L.polyline(points, {
            color: 'red',
            weight: 5,
            opacity: 0.7,
            dashArray:
