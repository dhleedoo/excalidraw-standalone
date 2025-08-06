# Excalidraw Standalone

🎨 **Excalidraw 로컬 실행용 패키지** - 협업 서버 포함

## 📁 구성

- `excalidraw/` - Excalidraw 웹 애플리케이션 (포트 8000)
- `collab/` - 실시간 협업 서버 (포트 3002)

## 📋 요구사항

- Node.js 18+
- Yarn (v1 또는 v2.4.2+)
- 
## 🚀 기본 실행 (웹서버)

### 1. Yarn이 없는 경우 먼저 설치
```bash
npm install -g yarn
```

### 2. Excalidraw 웹서버 의존성 설치
```bash
cd excalidraw
yarn install
```

### 3. Excalidraw 웹서버 시작
```bash
npx http-server . -p 8000
```

### 4. 브라우저에서 접속
```
http://localhost:8000
```

## 👥 협업 기능 추가 (선택사항)

### 1. 협업 서버 의존성 설치
```bash
cd collab
yarn install
```

### 2. 협업 서버 시작 (별도 터미널)
```bash
yarn start
```
서버가 정상 실행되면 http://localhost:3002 에서 확인 가능

## ⚙️ 설정 변경

### 협업 서버 포트 변경
`collab/.env.production` 파일 수정:
```env
PORT=3002
CORS_ORIGIN=*
```

### Excalidraw 협업 서버 URL 변경
`excalidraw/config.json` 파일 수정:
```json
{
  "COLLAB_SERVER_URL": "http://localhost:3002",
  "CORS_ORIGIN": "*"
}
```

## 📝 특징

- ✅ **빌드 없이 설정 변경** - `config.json` 파일만 수정
- ✅ **실시간 협업** - 다중 사용자 동시 편집 지원  
- ✅ **로컬 실행** - 인터넷 연결 없이 사용 가능
- ✅ **윈도우 호환** - Windows 환경에서 테스트 완료


## 🔧 문제 해결

### http-server가 없는 경우
```bash
npm install -g http-server
```

### 포트 충돌시
```bash
# 포트 사용 확인 (윈도우)
netstat -ano | findstr :8000
netstat -ano | findstr :3002

# 다른 포트 사용
npx http-server . -p 9000
```

---

**원본**: [Excalidraw](https://github.com/excalidraw/excalidraw) | [Excalidraw Room](https://github.com/excalidraw/excalidraw-room)
