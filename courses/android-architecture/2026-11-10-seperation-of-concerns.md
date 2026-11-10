# [Android] Seperation of Concerns (관심사 분리)

> 날짜: 2026-11-10  
> Course: (Modern Android App Architecture)  
> Pathway / Codelab: (Architecture Overview)  
> 원문: https://developer.android.com/topic/architecture

## 1. 오늘의 학습 목표

- 오늘 이해하려는 질문 1개: 관심사의 분리 이해, Activity에 왜 로직을 집중 시키면 안되는가?

## 2. 오늘 이해한 내용

- **핵심 개념:관심사의 분리란? (Seperation Of Concerns)
    - 클래스 혹은 계층 마다 명확한 책임을 부여하는 설계 원칙
    - 관심사 분리 없이 Activity 등의 컴포넌트에 모든 비즈니스 로직을 정의하면 생명 주기 변화에 취약 및 유지보수의 어려움 발생
- **왜 필요한가:
    - 관심사를 분리함으로써 명확하게 정의된 책임을 따라 코드를 분리할 수 있다. 
    - 개별 컴포넌트의 테스트가 쉬워진다.
    - 변경의 영향을 적게 받을 수 있다.

- **기존에 알던 방식과 다른 점:X

## 3. 코드 또는 예시 (선택)

```kotlin
class MainActivity : ComponentActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)

        // Activity가 데이터 저장 책임까지 담당
        val preferences = getSharedPreferences(
            "settings",
            MODE_PRIVATE
        )

        preferences.edit()
            .putBoolean("isEnabled", true)
            .apply()
    }
}
```

- 코드가 보여주는 동작: Activity 내에서 데이터 저장까지 수행
- 검증 상태: **미실행**
- 직접 실행했다면 환경과 결과:

## 4. 실무 연결 / 의문점 (선택)

- 내 프로젝트에 적용한다면: Jetpack Compose를 사용하면서 Single Activity 활용도가 높아져 Activity는 코드를 최소화 할 것, 데이터 저장은 별도의 Layer를 구축하여 구현
- 아직 헷갈리는 부분: x

## 5. 1분 복습

**Q. 오늘 배운 개념을 문서를 보지 않고 설명할 수 있는가?**

A. Yes

**오늘의 한 줄 요약:**
> 코드 구현 이전 가장 먼저 생각할 부분은 관심사의 분리이다 => 앱 아키텍쳐 설계의 뼈대

**다음에 볼 내용:**
- SSOT (Single Source Of Truth)

## 참고

- [공식 문서] (https://developer.android.com/topic/architecture)
