# 항해 플러스 프론트엔드 4기 과제 6주차 <br/>: Chapter 2-3. 관심사 분리와 폴더구조
- [과제 설명](#과제-설명)
  - [기본과제: 상태관리를 사용하여 관심사를 분리하고 FSD 폴더 구조를 적용하기](#기본과제-상태관리를-사용하여-관심사를-분리하고-FSD-폴더-구조를-적용하기)
  - [심화과제: TanstackQuery를 이용하여 코드를 개선하기](#심화과제-TanstackQuery를-이용하여-코드를-개선하기)
- [과제 체크포인트](#과제-체크포인트)
    - [기본과제](#기본과제)
    - [심화과제](#심화과제)
- [과제 셀프회고](#과제-셀프회고)
    - [과제에서 좋았던 부분](#과제에서-좋았던-부분)
      
## 과제 설명

여러분은 게시판을 관리할 수 있는 Admin 코드를 인수인계 받았습니다. 다행히 못 알아볼 정도의 더티코드는 아니고 적당히 잘 만든 것 같지만 정리가 된 것 같지 않은 아주 현실감 있는 익숙한 느낌의 코드였습니다.

우리는 지금까지 배웠던 내용을 토대로 해당 코드들을 클린하게 정돈하고 FSD 아키텍쳐를 활용해서 정리해보려고 합니다.

**여러분들은 해당 코드를 분석해보니 다음과 같은 문제점들을 발견할 수 있었습니다.**

1. 컴포넌트가 너무 크고 복잡하다.
2. Typescript를 사용하고 있지만 Type처리가 부실하다.
3. 상태관리의 개념없이 너무 많은 상태를 가지고 있다.
4. useEffect 관리가 안되고 있다.
5. 비동기 처리 로직이 복잡하게 구성되어 있다.

**여러분들은 해당 코드를 개선하기 위해서 다음과 같은 목표를 세웠습니다.**

1. Typescript를 확실히 사용해서 코드의 이해와 리팩토링에 대한 안정성을 확보합니다.
2. 컴포넌트에 단일 책임 원칙을 부여하여 작게 만들고자 합니다.
3. 적절한 관심사의 분리를 통해서 폴더구조를 만드려고 합니다.
4. 이때 배웠던 FSD를 한번 적용해보려고 합니다.

### 기본과제: 상태관리를 사용하여 관심사를 분리하고 FSD 폴더 구조를 적용하기

```markdown
목표:
전역상태관리를 이용한 적절한 분리와 계층에 대한 이해를 통한 FSD 폴더 구조 적용하기

- 전역상태관리를 사용해서 상태를 분리하고 관리하는 방법에 대한 이해
- Context API, Jotai, Zustand 등 상태관리 라이브러리 사용하기

- FSD(Feature-Sliced Design)에 대한 이해

- FSD를 통한 관심사의 분리에 대한 이해
- 단일책임과 역할이란 무엇인가?
- 관심사를 하나만 가지고 있는가?
- 어디에 무엇을 넣어야 하는가?
```

### 심화과제: TanstackQuery를 이용하여 코드를 개선하기

여러분들은 비동기 코드가 들어가고 서버와 통신을 하기 시작하니 상태관리가 엄청나게 복잡해진다는 것을 알았습니다. 그래서 서버상태관리를 도입을 하면 보다 함수형 패러다임으로 선언적으로 비동기를 관리할 수 있다는 사실을 알게 되었습니다.

**여러분들은 해당 코드를 개선하기 위해서 다음과 같은 목표를 세웠습니다.**

1. TanstackQuery를 이해하고 적용해보자.
2. api의 관리를 잘 할 수 있는 표준을 만들자.

```markdown
목표:
서버상태관리 도구인 TanstackQuery를 이용하여 비동기코드를 선언적인 함수형 프로그래밍으로 작성하기

- TanstackQuery의 사용법에 대한 이해
- TanstackQuery를 이용한 비동기 코드 작성에 대한 이해
- 비동기 코드를 선언적인 함수형 프로그래밍으로 작성하는 방법에 대한 이해
```

## 과제 체크포인트

### 기본과제

#### 목표 : 전역상태관리를 이용한 적절한 분리와 계층에 대한 이해를 통한 FSD 폴더 구조 적용하기
- 전역상태관리를 사용해서 상태를 분리하고 관리하는 방법에 대한 이해
- Context API, Jotai, Zustand 등 상태관리 라이브러리 사용하기
- FSD(Feature-Sliced Design)에 대한 이해
- FSD를 통한 관심사의 분리에 대한 이해
- 단일책임과 역할이란 무엇인가?
- 관심사를 하나만 가지고 있는가?
- 어디에 무엇을 넣어야 하는가?

#### 체크포인트
- [x] 전역상태관리를 사용해서 상태를 분리하고 관리했나요?
- [x] Props Drilling을 최소화했나요?
- [x] shared 공통 컴포넌트를 분리했나요?
- [x] shared 공통 로직을 분리했나요?
- [x] entities를 중심으로 type을 정의하고 model을 분리했나요?
- [x] entities를 중심으로 ui를 분리했나요?
- [x] entities를 중심으로 api를 분리했나요?
- [x] feature를 중심으로 사용자행동(이벤트 처리)를 분리했나요?
- [x] feature를 중심으로 ui를 분리했나요?
- [x] feature를 중심으로 api를 분리했나요?
- [x] widget을 중심으로 데이터를 재사용가능한 형태로 분리했나요?


### 심화과제

#### 목표: 서버상태관리 도구인 TanstackQuery를 이용하여 비동기코드를 선언적인 함수형 프로그래밍으로 작성하기 

- TanstackQuery의 사용법에 대한 이해
- TanstackQuery를 이용한 비동기 코드 작성에 대한 이해
- 비동기 코드를 선언적인 함수형 프로그래밍으로 작성하는 방법에 대한 이해

#### 체크포인트

- [ ] 모든 API 호출이 TanStack Query의 useQuery와 useMutation으로 대체되었는가?
- [ ] 쿼리 키가 적절히 설정되었는가?
- [ ] fetch와 useState가 아닌 선언적인 함수형 프로그래밍이 적절히 적용되었는가?
- [ ] 캐싱과 리프레시 전략이 올바르게 구현되었는가?


## 과제 셀프회고

### 과제에서 좋았던 부분

> 🌈 FSD 아키텍처 활용하기

![image (1)](https://github.com/user-attachments/assets/79f85f92-b95d-44fd-b2d8-40603ec83b1c)

#### Layers

- app > ~~processes~~ > pages > widgets > feature > entities > shared
    - app
       - 전역 설정, 애플리케이션 로직 초기화
       - Provider, Router, Client 같은 HOC
    - pages
       - 라우터(주소)별로 나눈 페이지
    - widgets
       - layouts, feature의 묶음
       - 독립적으로 사용되는 UI 컴포넌트
    - feature
       - 비즈니스 가치를 전달하는 사용자 시나리오와 기능 
       - components (기능, 행위, 동작 / 동사)
    - entities
       -  비즈니스 엔티티 
       - components (데이터 / 명사)
    - shared
       - 특정 비즈니스 로직에 종속되지 않은 재사용한 컴포넌트 및 유틸리티
       - 공유 컴포넌트
       - util, hooks, type, ui
       - Slice: 없음
 
![image (2)](https://github.com/user-attachments/assets/b9d5b24e-539a-4ed7-9641-031fcca17f5c)

- 위 레이어는 아래 레이어만 활용할 수 있습니다.
- 이 구조에서 features 레이어가 entities 레이어보다 더 위에 있기 때문에 entities 레이어는 features 레이어의 기능을 사용할 수 없습니다.
- 이는 한 방향으로만 향하는 선형적인 흐름을 유지하기 위함입니다.

#### Slice

- 슬라이스의 주요 목표는 코드를 값별로 그룹화 하는 것입니다.
- 슬라이스 이름은 프로젝트의 비즈니스 영역에 따라 결정되므로 표준화 되어있지 않습니다.
- 이 디렉토리에 있는 코드는 직접적으로 공유되자 않아야 합니다.

#### Segments

- api: 필요한 서버 요청
- ui: 슬라이스의 UI 컴포넌트
- model: 비즈니스 로직, 상태와의 상호작용
- lib: 슬라이스 내에서 사용되는 보조 기능
- config: 슬라이스에 필요한 구성 값
- consts: 슬라이스에 필요한 상수
