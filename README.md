<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nam Yoonjeong - Web3 Developer Portfolio</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Silkscreen&display=swap');

        body {
            font-family: 'VT323', monospace;
            background-color: #0a0a2a;
            color: #00ff00;
            line-height: 1.6;
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }

        h1, h2 {
            font-family: 'Silkscreen', cursive;
            color: #ff00ff;
        }

        .container {
            background-color: #000033;
            border: 2px solid #00ff00;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 0 10px #00ff00;
        }

        .pixel-art {
            image-rendering: pixelated;
            width: 100px;
            height: 100px;
        }

        ul {
            list-style-type: none;
            padding-left: 0;
        }

        li::before {
            content: "➜ ";
            color: #ff00ff;
        }

        a {
            color: #00ffff;
            text-decoration: none;
        }

        a:hover {
            text-decoration: underline;
        }

        .papers {
            background-color: #001a1a;
            border: 1px dashed #00ffff;
            padding: 10px;
            margin-top: 20px;
        }

        .chart-container {
            background-color: #001a1a;
            border: 1px dashed #00ffff;
            padding: 10px;
            margin-top: 20px;
        }
    </style>
    <!-- Chart.js 라이브러리 추가 -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body>
    <div class="container">
        <h1>Luke Nam</h1>
        <h2>Web3 Developer Extraordinaire</h2>
        <p>Email: <a href="mailto:nyj5404@yonsei.ac.kr">nyj5404@yonsei.ac.kr</a></p>
        <p>Github: <a href="https://github.com/nam2ee">Luke Nam</a></p>

        <h2>About Me</h2>
        <p>I am a Web3 developer with a passion for blockchain technology and decentralized applications. My expertise includes smart contract development, front-end and back-end integration, and blockchain core. Even I'm fully interested in AI X Crypto intergration.</p>

        <h2>Skills</h2>
        <ul>
            <li>Blockchain Core Development</li>
            <li>Smart Contracts</li>
            <li>Zero-Knowledge Proof</li>
            <li>AI Engineering, Jailbreaking</li>
            <li>Rust, Solidity, Javascript, Python</li>
            <li>React, ethers.js</li>
        </ul>

       
    </div>

    <div class="container">
        <h2>🚀 Experience & Achievements</h2>
        <ul>
            <li>Currently studying Computer Science at Yonsei University</li>
            <li>Blockchain At Yonsei Tech Lead</li>
            <li>Blockchain at Yonsei Alumni</li>
            <li>Former AI Engineer at AIM intelligence</li>
            <li>Recipient of Mina Protocol Grants</li>
            <li>Runner-up in the Generative AI Red Teaming Challenge by the Ministry of Science and ICT</li>
            <li>2nd Prize at Klaymakers 2023 (Backend, Smart Contract Engineer)</li>
            <li>XRPL Korean docs contributor</li>
            <li>Backend and Smart Contract Engineer for XRPL-EVM side chain lending protocol</li>
            <li>Klaytn Foundation Dev Ambassador</li>
            <li>Arbitrum Foundation Ambassador</li>
        </ul>
    </div>


        <div class="chart-container">
            <canvas id="cryptoChart"></canvas>
        </div>
    </div>

    <script>
        // Chart.js 초기 설정
        const ctx = document.getElementById('cryptoChart').getContext('2d');
        const cryptoChart = new Chart(ctx, {
            type: 'line',
            data: {
                labels: Array.from({ length: 50 }, (_, i) => i + 1),
                datasets: [
                    {
                        label: 'Bitcoin (BTC)',
                        borderColor: 'rgba(255, 99, 132, 1)',
                        backgroundColor: 'rgba(255, 99, 132, 0.2)',
                        data: Array.from({ length: 50 }, () => Math.floor(Math.random() * 10000) + 20000)
                    },
                    
                    {
                        label: 'Ethereum (ETH)',
                        borderColor: 'rgba(54, 162, 235, 1)',
                        backgroundColor: 'rgba(54, 162, 235, 0.2)',
                        data: Array.from({ length: 50 }, () =>  Math.floor(Math.random() * 10000) + 20000)
                    },
                    /*
                    {
                        label: 'Solana (SOL)',
                        borderColor: 'rgba(75, 192, 192, 1)',
                        backgroundColor: 'rgba(75, 192, 192, 0.2)',
                        data: Array.from({ length: 50 }, () =>  Math.floor(Math.random() * 1000) + 2000)
                    },
                    {
                        label: 'Ripple (XRP)',
                        borderColor: 'rgba(153, 102, 255, 1)',
                        backgroundColor: 'rgba(153, 102, 255, 0.2)',
                        data: Array.from({ length: 50 }, () =>  Math.floor(Math.random() * 1000) + 2000)
                    },
                    {
                        label: 'Near Protocol(NEAR)',
                        borderColor: 'rgba(255, 159, 64, 1)',
                        backgroundColor: 'rgba(255, 159, 64, 0.2)',
                        data: Array.from({ length: 50 }, () =>  Math.floor(Math.random() * 1000) + 2000)
                    }
                    */
                ]
            },
            options: {
                responsive: true,
                scales: {
                    x: {
                        display: true,
                        title: {
                            display: true,
                            text: 'Time'
                        }
                    },
                    y: {
                        display: true,
                        title: {
                            display: true,
                            text: 'Price (USD)'
                        }
                    }
                }
            }
        });

        // 데이터 업데이트 함수
        function updateData() {
            cryptoChart.data.datasets.forEach(dataset => {
                dataset.data.shift();
                dataset.data.push(Math.floor(Math.random() * 10000) + 20000);
            });
            cryptoChart.update();
        }

        // 1초마다 데이터 업데이트
        setInterval(updateData, 100);
    </script>
</body>
</html>
