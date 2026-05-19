## 포치타 설정 방법

### 1. 설치 (Windows)

setup.exe를 **관리자 권한**으로 실행 → Windows 서비스 자동 등록 + 트레이 앱 시작

기본 설치 경로:
- 프로그램: `C:\Program Files\Pochita`
- 설정: `C:\Program Files\Pochita\settings.json`
- SHOP.ini: EasyCard 설치 경로 (보통 `C:\Kicc\EasyCardK\SETUP\SHOP.ini`)

---

### 2. settings.json 설정

```json
{
  "port": 6767,
  "useMock": false,
  "easycardUrl": "http://localhost",
  "shopIniPath": "C:\\Kicc\\EasyCardK\\SETUP\\SHOP.ini"
}

```

| 키 | 기본값 | 설명 |
|---|---|---|
| `port` | `6767` | 서버 포트 |
| `useMock` | `false` | `true` → 실제 단말기 없이 Mock 동작 |
| `easycardUrl` | `http://localhost` | EasyCard 로컬 서버 주소 |
| `shopIniPath` | SHOP.ini | EasyCard의 SHOP.ini 파일 경로 (절대경로 권장) |

**`shopIniPath` 예시:**
```json
"shopIniPath": "C:\\Kicc\\EasyCardK\\SETUP\\SHOP.ini"
```

---

### 3. 동작 확인

```http
GET http://localhost:6767/health
```
응답: `{ "status": "ok" }`

---

### 4. 환경 변수로도 제어 가능

| 변수 | 설명 |
|---|---|
| `PORT` | 포트 번호 |
| `USE_MOCK=true` | Mock 모드 강제 활성화 |
| `EASYCARD_URL` | EasyCard 서버 주소 |
