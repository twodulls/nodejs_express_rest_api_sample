# nodejs_express_rest_api_sample
API Test를 수행하면서 API에 대한 궁금증이 생겨 손쉽게 API를 생성하기 위해 NodeJS를 이용하여 API를 생성한 샘플 코드

---

## 기술 스택

- **Runtime**: Node.js
- **Framework**: Express ~4.22.1
- **Template Engine**: Jade ~1.11.0
- **Middleware**: body-parser, cookie-parser, morgan

## 프로젝트 구조

```
nodejs_express_rest_api_sample/
├── app.js                  # Express 앱 설정 및 미들웨어 구성
├── bin/
│   └── www                 # 서버 실행 진입점 (기본 포트: 3000)
├── controllers/
│   └── index.js            # API 핸들러 함수 모음
├── routes/
│   ├── index.js            # 메인 라우터
│   └── users.js            # 유저 라우터
├── views/                  # Jade 템플릿
├── public/                 # 정적 파일
└── package.json
```

## 설치 및 실행

```bash
# 의존성 설치
npm install

# 서버 실행
npm start
```

서버는 기본적으로 **http://localhost:3000** 에서 실행됩니다.  
환경변수 `PORT`를 설정하면 포트를 변경할 수 있습니다.

## API 엔드포인트

| Method | Path          | 설명                            | 응답 예시                      |
|--------|---------------|---------------------------------|--------------------------------|
| GET    | `/`           | 기본 상태 확인 API              | `{ "success": true }`         |
| GET    | `/test`       | 테스트용 GET API                | `{ "message": "test" }`       |
| POST   | `/post_test`  | 요청 body를 그대로 반환하는 API | `{ "message": "<요청값>" }`   |
| GET    | `/users`      | 유저 리소스 (기본 응답)         | `respond with a resource`     |

### POST `/post_test` 요청 예시

```bash
curl -X POST http://localhost:3000/post_test \
  -H "Content-Type: application/json" \
  -d '{"message": "hello"}'
```

**응답:**
```json
{
  "message": "hello"
}
```
