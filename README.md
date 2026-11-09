# Android Official TIL

Google Android Developers의 공식 Courses / Pathway / Codelab을 직접 공부하고 **내 언어로 이해한 내용**을 기록하는 저장소입니다.

> 원칙: 학습은 사람이, AI는 피드백과 복습을 돕는 도구로 사용합니다.

## 목표

- 하루 10분 공식 자료 읽기 + 20~30분 Markdown 정리
- Android의 동작 원리, 설계 근거, 실무 적용 지점 이해
- 필요할 때 Codex/Claude Code로 설명 검토, 추가 질문, 복습 퀴즈 생성
- 별도 Issue·PR·Actions 없이 `main` 브랜치에 직접 커밋

## 폴더 구성

```text
android-official-til/
├── README.md
├── COURSES.md                 # 공식 학습 링크
├── AGENTS.md                  # Codex용 저장소 지침
├── CLAUDE.md                  # Claude Code용 저장소 지침
├── .gitignore
├── templates/
│   └── DAILY_TIL.md           # 오늘의 TIL 틀
├── prompts/
│   └── AI_STUDY_PROMPTS.md    # 복사해서 쓸 AI 프롬프트
└── courses/
    ├── android-architecture/
    │   └── example-single-source-of-truth.md
    ├── jetpack-compose/
    ├── android-basics-compose/
    ├── accessibility/
    └── kotlin-multiplatform/
```

## 시작하는 법

1. `COURSES.md`의 **Android App Architecture**에서 학습할 소제목을 고릅니다.
2. `templates/DAILY_TIL.md`를 복사해 `courses/android-architecture/YYYY-MM-DD-topic.md`로 저장합니다.
3. **먼저 직접** 학습 목표와 핵심 이해 내용을 작성합니다.
4. 실습을 했다면 코드와 실행 결과를 적고, 하지 않았다면 `미실행`으로 명시합니다.
5. Codex 또는 Claude Code에 `prompts/AI_STUDY_PROMPTS.md`의 검토/퀴즈 프롬프트를 전달합니다.
6. AI의 제안을 **직접 확인한 뒤** 필요한 내용만 반영합니다.
7. `main` 브랜치에서 커밋합니다.

```bash
git status
git add courses/android-architecture/YYYY-MM-DD-topic.md
git commit -m "docs(til): study single source of truth"
git push origin main
```

처음 커밋과 원격 저장소 연결 방법은 이 문서의 아래 항목을 참조하세요.

## 신규 GitHub 저장소 연결

1. GitHub의 **New repository**에서 `android-official-til` 생성 (Public 또는 Private 선택).
2. 로컬 파일을 업로드할 예정이므로 GitHub 쪽에서 **README / .gitignore / License 초기 생성은 체크하지 않습니다.**
3. 압축을 해제한 저장소 폴더에서 아래 명령을 실행합니다.

```bash
git init -b main
git add .
git commit -m "chore: initialize Android official TIL"
git remote add origin https://github.com/<YOUR_USERNAME>/android-official-til.git
git push -u origin main
```

`<YOUR_USERNAME>`은 자신의 GitHub 사용자명으로 바꿔주세요. 이미 로컬 Git 저장소가 있다면 `git init`은 생략합니다. HTTPS push에는 GitHub 로그인이 필요할 수 있습니다.

## 파일명 규칙

- 기본: `2026-11-06-single-source-of-truth.md`
- 다음 날 같은 주제 추가 학습: `2026-11-07-single-source-of-truth-part-02.md`
- 실습은 별도 파일로 분리 가능: `2026-11-08-compose-state-codelab.md`
- **파일 하나의 길이 때문에 무조건 분리하지 않습니다.** 서로 다른 학습 질문일 때 분리합니다.

## TIL을 작성할 때의 기준

- 문서를 길게 복사하지 않습니다. 내 언어로 다시 설명합니다.
- **공식 문서 내용 / 개인적인 해석 / 직접 실행한 결과**를 분리합니다.
- Kotlin 코드가 실제로 실행되었는지 분명히 적습니다.
- 학습이 적었던 날에는 5~10줄이어도 괜찮습니다.
- 회사 코드·로그·고객 정보는 저장소에 넣지 않습니다.
- AI의 설명이나 정답을 공식 문서와 비교해 오류를 확인합니다.

## 참고

- [Android Developers Courses](https://developer.android.com/courses?hl=ko)
- [GitHub 새 저장소 만들기](https://docs.github.com/ko/repositories/creating-and-managing-repositories/creating-a-new-repository)
