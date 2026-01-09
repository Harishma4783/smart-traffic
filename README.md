![imageharish](https://github.com/user-attachments/assets/9ad2edd2-bb8b-485b-b71d-e660cacfcecd)
![pic1](https://github.com/user-attachments/assets/e62c84d4-e063-41f1-bd3f-d70c4d24443c)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Smart Traffic Signal System</title>

    <style>
        body {
            font-family: Arial;
            background-color: #0f172a;
            color: white;
            text-align: center;
            padding: 20px;
        }

        h1 {
            color: #38bdf8;
        }

        .road {
            background: #1e293b;
            padding: 15px;
            margin: 10px auto;
            width: 320px;
            border-radius: 10px;
        }

        input {
            width: 80px;
            padding: 5px;
        }

        button {
            padding: 10px 20px;
            background: #22c55e;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            margin-top: 20px;
        }

        button:hover {
            background: #16a34a;
        }

        .green {
            color: #22c55e;
            font-weight: bold;
        }

        .red {
            color: #ef4444;
            font-weight: bold;
        }
    </style>
</head>

<body>

<h1>🚦 Smart Traffic Signal System</h1>

<div class="road">
    Road A Vehicles:
    <input type="number" id="a" value="0">
</div>

<div class="road">
    Road B Vehicles:
    <input type="number" id="b" value="0">
</div>

<div class="road">
    Road C Vehicles:
    <input type="number" id="c" value="0">
</div>

<div class="road">
    Road D Vehicles:
    <input type="number" id="d" value="0">
</div>

<button onclick="startTraffic()">Start Traffic</button>

<div id="output"></div>

<script>
    function greenTime(count) {
        if (count > 50) return 20;
        if (count > 30) return 15;
        if (count > 10) return 10;
        return 5;
    }

    async function startTraffic() {
        let roads = [
            { name: "Road A", vehicles: Number(a.value) },
            { name: "Road B", vehicles: Number(b.value) },
            { name: "Road C", vehicles: Number(c.value) },
            { name: "Road D", vehicles: Number(d.value) }
        ];

        let output = document.getElementById("output");
        output.innerHTML = "<h2>🚦 Traffic Started</h2>";

        for (let road of roads) {![imageharish](https://github.com/user-attachments/assets/de64e175-17d5-4bab-a43f-313c1a3f4c6a)

            let time = greenTime(road.vehicles);

            output.innerHTML += `
                <p class="green">
                    ${road.name} → GREEN (${time} seconds) | Vehicles: ${road.vehicles}
                </p>
            `;

            await new Promise(resolve => setTimeout(resolve, time * 1000));

            output.innerHTML += `
                <p class="red">
                    ${road.name} → RED
                </p>
            `;
        }

        output.innerHTML += "<h3>✅ Traffic Cycle Completed</h3>";
    }
</script>

</body>
</html>
# smart-traffic
smart traffic mini project
