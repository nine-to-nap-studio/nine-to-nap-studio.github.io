# Nine to Nap Studio — 공개 사이트

게임의 개인정보처리방침과 `app-ads.txt` 를 올리는 **공개** 사이트. 게임 소스는 각 게임의 private 레포에 있고, 여기엔 공개해도 되는 파일만 둔다.

- 주소: https://nine-to-nap-studio.github.io/
- 레포: GitHub 조직 `nine-to-nap-studio` 의 공개 레포 `nine-to-nap-studio.github.io`
- 이 레포 커밋 작성자 이름은 `Nine to Nap Studio` 로 설정해 둠 (`git config user.name`, 이 폴더에만 적용)

## 파일

| 파일 | 공개 주소 | 용도 |
|---|---|---|
| `index.html` | `/` | 개발자 소개·게임 목록·연락처. Play 스토어 "웹사이트" 칸에 이 주소를 넣음 |
| `star-merge/privacy.html` | `/star-merge/privacy.html` | 별 머지 개인정보처리방침 (한국어) |
| `star-merge/privacy-en.html` | `/star-merge/privacy-en.html` | 영어 번역 |
| `app-ads.txt` | `/app-ads.txt` | AdMob 인증 판매자 목록. **반드시 루트**에 있어야 AdMob 이 찾음 |
| `style.css` | | 공통 스타일 |
| `.nojekyll` | | GitHub Pages 가 파일을 가공하지 않고 그대로 내보내게 함 |

## 처음 올리기

1. GitHub 에서 조직 만들기: https://github.com/account/organizations/new?plan=free
   - 이름 `nine-to-nap-studio`, 소유는 본인 개인 계정
   - 조직 → Settings → Member privileges 와 People 에서 멤버 공개 여부 확인 (멤버를 비공개로 두면 조직 페이지에 개인 계정이 안 보임)
2. 조직 안에 **공개(Public)** 레포 `nine-to-nap-studio.github.io` 만들기 (README·.gitignore 체크 해제)
3. 이 폴더에서 push
   ```bash
   cd ~/myProjects/game-site
   git remote add origin git@github.com:nine-to-nap-studio/nine-to-nap-studio.github.io.git
   git push -u origin main
   ```
4. 1~2분 뒤 https://nine-to-nap-studio.github.io/ 확인. `조직이름.github.io` 레포는 기본 브랜치가 자동으로 사이트가 됨 (안 뜨면 레포 Settings → Pages → Source: Deploy from a branch, `main` / `(root)`)

## AdMob 게시자 ID 넣기

AdMob 가입 후 [설정 → 계정 정보 → 게시자 ID] 의 `pub-` 로 시작하는 값을 `app-ads.txt` 의 `pub-XXXXXXXXXXXXXXXX` 자리에 넣고 push. AdMob 이 확인하는 데 최대 24시간.

## 다음 게임 추가

1. `star-merge/` 폴더를 복사해 새 게임 폴더(예: `next-game/`) 만들기
2. `privacy.html`·`privacy-en.html` 의 게임 이름·처리 항목을 그 게임에 맞게 수정 (광고 SDK 가 같으면 대부분 그대로)
3. `index.html` 게임 목록에 카드 추가
4. 같은 AdMob 계정이면 `app-ads.txt` 는 그대로 (게시자 ID 는 계정 단위)

## 주의

- 공개 레포라 커밋 이력까지 누구나 볼 수 있음. 키·비밀번호·실명·게임 소스는 넣지 말 것
- 커밋 이메일이 GitHub 계정에 등록된 이메일이면, GitHub 가 커밋 작성자를 그 계정과 연결해 보여 줌
