# 대회연습용 조종 시뮬레이터 (WRL · RoboRAVE)

MRC 축구 · 로보레이브 SoccerBot RC · 로봇배틀 오셀로를 크롬에서 연습하는 3D 조종 시뮬레이터입니다.
규칙은 worldrobotleague.net 기준이며, 물리엔진은 cannon-es, 3D는 three.js를 씁니다.

## 파일
| 파일 | 내용 |
|---|---|
| `index.html` | 시뮬레이터 본체 |
| `ldraw-lib.js` | 내장 LDraw 부품 (EV3 · SPIKE · Robot Inventor 세트 부품, 로보메이커스 캐드와 같은 데이터) |

두 파일을 **같은 폴더**에 두어야 합니다.

## GitHub Pages에 올리기
1. GitHub에서 새 저장소를 만듭니다 (예: `robot-sim`). 기존 `mindstorms-cad` 저장소 안의 하위 폴더(예: `sim/`)에 넣어도 됩니다.
2. `index.html`, `ldraw-lib.js`, `README.md`를 올립니다 (Add file → Upload files).
3. 새 저장소라면 Settings → Pages → Branch: `main` / `(root)` → Save.
4. 1~2분 뒤 주소로 접속합니다.
   - 새 저장소: `https://daewonlee81-glitch.github.io/robot-sim/`
   - 하위 폴더: `https://daewonlee81-glitch.github.io/mindstorms-cad/sim/`

## 온라인 대전
1. 방장 PC: **온라인 탭 → 방 만들기** → 5자리 방 코드가 표시됩니다.
2. 다른 PC·태블릿: 같은 주소를 열고 **온라인 탭 → 방 코드 입력 → 참가**.
3. 방장이 종목·인원·로봇 모델·경기 시작을 정합니다. 참가자는 자기 로봇만 조종합니다.
4. 사람이 없는 자리는 AI가 움직입니다 (경기 탭의 상대/팀원 AI 설정).
5. 참가자가 로봇 모델 탭에서 파일을 고르면 그 모델이 방장에게 전송되어 내 자리 로봇에 적용됩니다.

- 연결 방식: WebRTC 직접 연결. 처음 서로를 찾을 때만 PeerJS 공개 서버(0.peerjs.com)를 씁니다.
- 방장 기기가 물리 계산을 하므로 가장 성능 좋은 PC를 방장으로 하세요.
- 학교·기관 네트워크 방화벽에 따라 연결이 안 될 수 있습니다. 이때는 휴대폰 핫스팟 등 다른 네트워크로 시험해 보세요.
- Claude 미리보기 화면에서는 외부 연결이 막혀 있어 온라인 대전이 되지 않습니다.

## 조종 (엑스박스 컨트롤러 · 대회 방식)
| 입력 | 동작 |
|---|---|
| RT | 액셀 (누르는 깊이만큼) |
| D패드 ← / → | 방향 전환 (제자리 회전 가능) |
| D패드 ↓ | 누르는 동안 후진 |
| LT | 비상정지 |
| A | MRC 축구: 슛(킥 모터) · 오셀로: 블록 뒤집기 |
| Y / X | 카메라 전환 / 내 로봇 추적 |
| View / Menu | 재배치 / 일시정지 (방장만) |

- 화면 왼쪽 아래 스위치(또는 G 키)로 컨트롤러 연결을 켭니다.
- 태블릿은 조작 탭에서 **터치 조종 버튼**을 켜면 화면에 ◀ ▼ ▶ / LT / A / RT 버튼이 나옵니다. 터치 기기에서는 처음부터 켜져 있습니다.

## 저작권 표기
- 부품 데이터: LDraw.org Parts Library (CC BY 4.0)
- three.js (MIT), cannon-es (MIT), PeerJS (MIT)
