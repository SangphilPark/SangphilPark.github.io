---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
layout: default
---

<br>

---

# ✨[경험 정리 포트폴리오 링크](https://drive.google.com/file/d/1Kdr9NtZQsK8bcOs_UXwaUCU-vgJkYnnq/view?usp=drive_link)

<!-- ![image](https://github.com/SangphilPark/SangphilPark.github.io/assets/81211140/8a6d4f8d-36f8-486d-a0ec-a70d5bf4fe9e)

![image](https://github.com/SangphilPark/SangphilPark.github.io/assets/81211140/7718db01-04cc-461b-a4d7-77e08cf6075f)

> Add Markdown syntax content to file `_tabs/about.md`{: .filepath } and it will show up on this page.
> {: .prompt-tip } -->


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vertical Line Example</title>
    <style>
        body {
            line-height: 1.6;
            margin: 0;
            padding: 0;
            background-color: #f0f0f0;
            color: #333;
        }
        .container {
            width: 100%;
            margin: 20px auto;
            font-family: Arial, sans-serif;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            overflow: hidden;
            display: flex;
            flex-wrap: wrap;
        }
        .skills {
            width: 100%;
            margin-bottom: 1rem;
            background-color: #f8f9fa;
            border-bottom: 1px solid #dee2e6;
            text-align: center;
        }
        .skills ul {
            list-style-type: none;
            padding: 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
        }
        .skills li {
            margin: 10px;
            padding: 10px 17px;
            background-color: #495057;
            color: #fff;
            border-radius: 20px;
            text-transform: uppercase;
            font-weight: bold;
            font-size: 11px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            position: relative;
            background-image: linear-gradient(45deg, rgba(255,255,255,0.1) 25%, transparent 25%, transparent 50%, rgba(255,255,255,0.1) 50%, rgba(255,255,255,0.1) 75%, transparent 75%, transparent);
            background-size: 30px 30px;
            animation: shine 2s infinite linear;
        }
        .skills li:hover {
            background-color: #343a40;
        }
        .skills li:nth-child(2n) {
            background-color: #fc84ce;
        }
        .skills li:nth-child(3n) {
            background-color: #663cfd;
        }
        .skills li:nth-child(4n) {
            background-color: #4e5ee9;
        }
        .skills li:nth-child(5n) {
            background-color: #2fdfdf;
        }
        .skills li:nth-child(6n) {
            background-color: #b9e05d;
        }
        .skills li:nth-child(8n) {
            background-color: #c53737;
        }
        @keyframes shine {
            to {
                background-position: 30px 0;
            }
        }
        .timeline {
            width: 100%;
            margin-bottom: 1rem;
            padding: 2rem;
            background-color: #f8f9fa;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            position: relative;
            overflow: hidden;
        }
        .event {
            position: relative;
            display: flex;
            align-items: center;
            margin-bottom: 50px;
        }
        .event:before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 20px;
            height: 20px;
            background-color: #007bff;
            border-radius: 50%;
            border: 2px solid #fff;
            transform: translate(-50%, -50%);
        }
        .event-content {
            margin-left: 30px;
            font-size: 14px;
        }
        .timeline-line {
            position: absolute;
            left: 10px;
            width: 2px;
            background-color: #007bff;
            z-index: -1;
            height: calc(100% + 20px); /* +20px for the space above and below events */
        }
        .timeline-container {
            position: relative;
            width: 100%;
        }
        .section {
            width: 100%;
            margin-bottom: 1rem;
            padding: 1rem;
        }
        .section h2 {
            color: #007bff;
            margin-bottom: 20px;
        }
        .section p {
            margin-bottom: 10px;
        }
        .section ul {
            list-style-type: none;
            padding: 0;
        }
        .section li {
            margin-bottom: 5px;
        }
        .awards {
            width: 90%;
            padding: 1rem;
        }
        .awards h2 {
            color: #007bff;
            margin-bottom: 20px;
        }
        .goals {
            width: 95%;
            padding: 20px;
        }
        .goals h2 {
            color: #007bff;
            margin-bottom: 20px;
        }
        .container-body {
            display: flex;
            justify-content: space-around;
            width: 100%;
            margin-bottom: 30px;
            position: relative;
            overflow: hidden;
        }
        .container-right {
            margin-left: 2rem;
            display: flex;
            flex-direction: column;
            width: 100%;
            margin-bottom: 30px;
            position: relative;
            overflow: hidden;
            background-color: #f8f9fa;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="skills">
            <h2>Skills</h2>
            <ul>
                <li>SpringBoot</li>
                <li>Java</li>
                <li>백엔드</li>
                <li>PyThon</li>
                <li>컴퓨터비전</li>
                <li>자연어처리</li>
                <li>NoSQL</li>
                <li>VectorDB</li>
            </ul>
        </div>
        <div class="container-body">
            <div class="timeline-container">
                <div class="timeline">
                    <h2>경험 타임라인</h2>
                    <div class="timeline-line"></div>
                    <div class="event">
                        <div class="event-content">
                            <h3>삼성 청년 SW 아카데미</h3>
                            <p>자바 기반 웹 프레임워크</p>
                            <p>Date: 24.06</p>
                        </div>
                    </div>
                    <div class="event">
                        <div class="event-content">
                            <h3>Google ML BootCamp</h3>
                            <p>Tensorflow 기반 모델링</p>
                            <p>Date: 23.12</p>
                        </div>
                    </div>
                    <div class="event">
                        <div class="event-content">
                            <h3>네이버부스트캠프</h3>
                            <p>Computer Vision 엔지니어링</p>
                            <p>Date: 23.08</p>
                        </div>
                    </div>
                </div>
            </div>
            <div class="container-right">
                <div class="section awards">
                    <h2>Awards</h2>
                    <ul>
                        <li>Kaggle 텐서플로우 머신러닝 대회 Top 3%</li>
                        <li>홍익대바이오헬스 사랑니 발치 시간 예측 대회 수상</li>
                        <li>(머신러닝, 딥러닝 가능해요)</li>
                    </ul>
                </div>
                <div class="section goals">
                    <h2>Goals</h2>
                    <p># 더 나은 개발 방법을 고민하고 나눠요</p>
                    <p># 팀플하면서 의견을 교류하는 법을 배우고 싶습니다!</p>
                    <p># 부족한 부분을 찾아서 완성도를 높여요</p>
                    <p># AI + IoT AIoT 프로젝트를 경험하고 싶습니다!</p>
                    <p># 웹 서비스 배포!</p>
                    <br>
                    <hr>
                    <!-- <p># 같이 하실 분 연락 주세요!!!</p>
                    <p>!!! 이왕 하는 거 즐기며 하자는 마인드로 열심히 참여하겠습니다 !!!</p> -->
                </div>
            </div>
        </div>
    </div>
</body>
</html>
