
# Technical-Document
---

# 📋 UE기술 포트폴리오 문서 — Ren-ame

> **작성일:** 2026-03-10  
> **GitHub:** [github.com/Ren-ame](https://github.com/Ren-ame)

---

## 1. 개요 (Overview)

본 문서는 **Unreal Engine C++ 게임 개발** 및 **DirectX 3D 그래픽스 프로그래밍** 학습/프로젝트 리포지토리 6개를 종합한 기술 문서입니다. 전체 프로젝트 흐름은 **UE C++ 기초 문법 → 3인칭 캐릭터(GAS-like) → 온라인 서브시스템 → Gameplay Ability System → 기타 고급 기능 + 에디터 플러그인 → DirectX 3D 렌더링**으로 이어지는 단계별 학습 로드맵을 반영합니다.

| # | Repository | 핵심 주제 | 주요 언어 | 생성일 |
|---|-----------|----------|----------|--------|
| 1 | [U04_BasicSyntaxCPP](https://github.com/Ren-ame/U04_BasicSyntaxCPP) | UE C++ 기초 문법 | C++ 97.8%, C# 1.8% | 2024-05-31 |
| 2 | [U05_ThirdPersonCPP](https://github.com/Ren-ame/U05_ThirdPersonCPP) | 3인칭 캐릭터 (GAS-like) | C++ 98.8% | 2024-06-20 |
| 3 | [U06_OSS](https://github.com/Ren-ame/U06_OSS) | Unreal Online Sub System | C++ 97.2%, C# 1.9% | 2024-07-22 |
| 4 | [U07_GAS](https://github.com/Ren-ame/U07_GAS) | Gameplay Ability System | C++ 98.1%, C# 1.3% | 2024-08-07 |
| 5 | [U08_Misc](https://github.com/Ren-ame/U08_Misc) | 에디터 플러그인 & 기타 고급 기능 | C++ 95.8%, C# 3.8% | 2024-09-19 |
| 6 | [Tore09_D3D](https://github.com/Ren-ame/Tore09_D3D) | DirectX 3D 렌더링 엔진 | C++ 65.7%, C 32.9%, HLSL 1.4% | 2024-10-16 |

---

## 2. 기술 스택 (Tech Stack)

### 🎮 게임 엔진
- **Unreal Engine** (C++ 기반, 5개 프로젝트)
- **UE Build System** — `.uproject`, `.Target.cs`, `.Build.cs`

### 🖥️ 그래픽스
- **Direct3D** — D3D 렌더링 파이프라인, Shader 프로그래밍
- **HLSL** — Vertex/Pixel Shader (`.fx` 쉐이더 파일)

### 💻 프로그래밍 언어
- **C++** (주력) — Unreal Engine C++ / Win32 / DirectX
- **C** — 네이티브 라이브러리 연동
- **C#** — UE Build System (`.Build.cs`, `.Target.cs`)
- **HLSL** — GPU 쉐이더 프로그래밍

### 🛠️ 도구 및 환경
- **Visual Studio 2019+** (Solution/Project 기반 빌드)
- **Git / GitHub** (버전 관리)

---

## 3. 프로젝트 상세

---

### 3.1 `U04_BasicSyntaxCPP` — UE C++ 기초 문법

| 항목 | 내용 |
|------|------|
| **설명** | UE C++의 기초 문법 |
| **리포** | [Ren-ame/U04_BasicSyntaxCPP](https://github.com/Ren-ame/U04_BasicSyntaxCPP) |
| **기간** | 2024.05 – 2024.06 |
| **프로젝트 파일** | `U04_ThirdPersonCPP.uproject` |

**디렉토리 구조:**
```
U04_BasicSyntaxCPP/
├── Config/                          # UE 프로젝트 설정
├── Content/                         # UE 에셋 (블루프린트, 레벨 등)
├── Source/
│   ├── U04_ThirdPersonCPP/         # 게임 모듈 소스 코드
│   ├── U04_ThirdPersonCPP.Target.cs
│   └── U04_ThirdPersonCPPEditor.Target.cs
└── U04_ThirdPersonCPP.uproject
```

**학습 범위:**
- UE C++ 클래스 생성 및 구조 이해 (`UCLASS`, `UPROPERTY`, `UFUNCTION`)
- 기본 게임 오브젝트 구현 (Actor, Component, GameMode)
- 언리얼 리플렉션 시스템 및 메모리 관리
- ThirdPerson 템플릿 기반 실습 환경 구축

---

### 3.2 `U05_ThirdPersonCPP` — 3인칭 캐릭터 시스템 (GAS-like)

| 항목 | 내용 |
|------|------|
| **설명** | GAS-like (Gameplay Ability System 유사 구현) |
| **리포** | [Ren-ame/U05_ThirdPersonCPP](https://github.com/Ren-ame/U05_ThirdPersonCPP) |
| **기간** | 2024.06 – 2024.07 |
| **프로젝트 파일** | `ThirdPersonCPP.uproject` |

**디렉토리 구조:**
```
U05_ThirdPersonCPP/
├── Config/
├── Content/
├── Source/
│   ├── ThirdPersonCPP/             # 게임 모듈 소스 코드
│   ├── ThirdPersonCPP.Target.cs
│   └── ThirdPersonCPPEditor.Target.cs
├── ThirdPersonCPP.uproject
└── PN_OpenWorldFoliage.png         # 오픈 월드 폴리지 관련 이미지
```

**핵심 구현 내용:**
- GAS(Gameplay Ability System)와 유사한 커스텀 어빌리티 시스템 설계
- 3인칭 캐릭터 컨트롤러 및 카메라 시스템
- 어빌리티 기반 캐릭터 행동 패턴 구현
- 오픈 월드 환경 내 Foliage 시스템 활용

---

### 3.3 `U06_OSS` — Unreal Online Sub System (멀티플레이어 네트워킹)

| 항목 | 내용 |
|------|------|
| **설명** | Unreal Online Sub System |
| **리포** | [Ren-ame/U06_OSS](https://github.com/Ren-ame/U06_OSS) |
| **기간** | 2024.07 – 2024.08 |
| **프로젝트 파일** | `OSS.uproject` |

**디렉토리 구조:**
```
U06_OSS/
├── Config/
├── Content/
├── Source/
│   ├── OSS/
│   │   ├── Actors/              # 네트워크 관련 액터
│   │   ├── Characters/          # 멀티플레이 캐릭터
│   │   ├── Game/                # 게임 모드/스테이트
│   │   ├── UI/                  # 네트워크 UI (로비, 세션 등)
│   │   ├── OSS.Build.cs         # 빌드 설정 (OnlineSubsystem 모듈 의존)
│   │   ├── OSSGameMode.cpp/h    # 커스텀 GameMode
│   │   └── OSS.cpp/h            # 모듈 엔트리
│   ├── OSS.Target.cs
│   └── OSSEditor.Target.cs
└── OSS.uproject
```

**핵심 구현 내용:**
- **Online Subsystem** 플러그인 활용 (Steam/Null 등)
- 세션 생성/검색/참가 (Create/Find/Join Session)
- 멀티플레이어 로비 UI 구현
- 네트워크 리플리케이션 및 RPC (Remote Procedure Call)
- 게임 모드/스테이트 네트워크 동기화

---

### 3.4 `U07_GAS` — Gameplay Ability System

| 항목 | 내용 |
|------|------|
| **설명** | Unreal GAS (Gameplay Ability System) 심화 |
| **리포** | [Ren-ame/U07_GAS](https://github.com/Ren-ame/U07_GAS) |
| **기간** | 2024.08 – 2024.09 |
| **프로젝트 파일** | `GAS.uproject` |
| **빌드 배포** | `WindowsNoEditor/` (패키징 빌드 포함) |

**디렉토리 구조:**
```
U07_GAS/
├── Config/
├── Content/
├── Source/
│   ├── GAS/
│   │   ├── AI/                  # AI 행동 트리 / 비헤이비어
│   │   ├── Actions/             # 커스텀 GameplayAbility 액션
│   │   ├── Characters/          # 캐릭터 (플레이어 + AI)
│   │   ├── Components/          # 어빌리티 시스템 컴포넌트
│   │   ├── Controller/          # Player/AI 컨트롤러
│   │   ├── Demo/                # 데모/테스트 레벨 관련
│   │   ├── Game/                # GameMode, GameState 등
│   │   ├── Interaction/         # 상호작용 시스템
│   │   ├── Projectiles/         # 투사체 시스템
│   │   ├── UI/                  # HUD, 위젯 UI
│   │   ├── GAS.Build.cs
│   │   ├── GASGameModeBase.cpp/h
│   │   └── GAS.cpp/h
│   ├── GAS.Target.cs
│   └── GASEditor.Target.cs
├── WindowsNoEditor/              # 패키징 빌드
└── GAS.uproject
```

**핵심 구현 내용:**
- **Gameplay Ability System (GAS)** 전체 파이프라인 구현
  - `UGameplayAbility`, `UAttributeSet`, `UAbilitySystemComponent`
- **AI 시스템** — Behavior Tree, AI Controller 기반 적 AI
- **투사체 시스템** — Projectile 기반 원거리 공격
- **상호작용 시스템** — 오브젝트와의 인터랙션 처리
- **컴포넌트 기반 설계** — 재사용 가능한 GameplayAbility 컴포넌트
- **UI 시스템** — 체력바, 어빌리티 슬롯 등 게임 HUD

---

### 3.5 `U08_Misc` — 에디터 확장 & 기타 고급 기능

| 항목 | 내용 |
|------|------|
| **설명** | 에디터 플러그인, RHI, 기타 고급 UE 기능 |
| **리포** | [Ren-ame/U08_Misc](https://github.com/Ren-ame/U08_Misc) |
| **기간** | 2024.09 – 2024.10 |
| **프로젝트 파일** | `Misc.uproject` |

**디렉토리 구조:**
```
U08_Misc/
├── Config/
├── Content/
├── Plugins/
│   └── Tore/                        # 커스텀 에디터 플러그인
│       ├── Tore.uplugin
│       └── Source/Tore/
│           ├── Tore.cpp/h           # 모듈 엔트리 (IModuleInterface)
│           ├── Tore.Build.cs
│           ├── ToolBar/             # 커스텀 툴바 버튼
│           │   ├── CButtonCommand   # UI 커맨드 정의
│           │   └── CIconStyle       # 커스텀 아이콘 스타일
│           ├── DetailPannel/        # 디테일 패널 커스터마이징
│           │   └── CDetailPannel    # IDetailCustomization
│           ├── DebuggerCategory/    # 게임플레이 디버거 카테고리
│           │   └── CDebuggerCategory
│           ├── AssetTools/          # 커스텀 에셋 타입
│           │   └── CMaterialData
│           └── AssetViewer/         # 커스텀 에셋 뷰어
│               └── CAssetViewer
├── Source/
│   ├── Misc/
│   │   ├── Miku/                    # 특정 기능 모듈
│   │   ├── RHI/                     # Rendering Hardware Interface 실습
│   │   ├── TP_TopDown/              # 탑다운 템플릿 관련
│   │   ├── Misc.Build.cs
│   │   └── MiscGameModeBase.cpp/h
│   ├── Misc.Target.cs
│   └── MiscEditor.Target.cs
└── Misc.uproject
```

**핵심 구현 내용:**

#### 🔌 `Tore` 에디터 플러그인
- **커스텀 툴바 버튼** — `FExtender`를 통한 레벨 에디터 툴바 확장
  - LoadMesh 버튼: 바이너리 메시 데이터(`.bin`) 로드
  - OpenViewer 버튼: 커스텀 에셋 뷰어 실행
- **커스텀 아이콘 스타일** — `FSlateStyleSet` 기반 아이콘 등록
- **디테일 패널 커스터마이징** — `IDetailCustomization` 구현
  - 색상 변경 버튼
  - 메시 데이터 바이너리 직렬화/역직렬화(Save/Load)
- **게임플레이 디버거** — `FGameplayDebuggerCategory` 커스텀 카테고리
  - 플레이어/전방 액터/디버그 액터 정보 실시간 표시
- **커스텀 에셋 타입** — `IAssetTypeActions` + 커스텀 카테고리 등록
- **커스텀 에셋 뷰어** — AdvancedPreviewScene 기반

#### 🔧 RHI (Rendering Hardware Interface)
- 언리얼 엔진 RHI 레이어 직접 접근 및 실습
- StaticMesh 버텍스/인덱스 버퍼 데이터 추출
- 메시 데이터 바이너리 직렬화 (`FBufferArchive`, `FMemoryReader`)

---

### 3.6 `Tore09_D3D` — DirectX 3D 그래픽스 엔진

| 항목 | 내용 |
|------|------|
| **설명** | Direct3D 기반 커스텀 렌더링 프레임워크 |
| **리포** | [Ren-ame/Tore09_D3D](https://github.com/Ren-ame/Tore09_D3D) |
| **기간** | 2024.10 |
| **솔루션** | `D3D/D3D.sln` (Visual Studio 2019) |

**디렉토리 구조:**
```
Tore09_D3D/
├── D3D/
│   ├── D3D.sln                      # Visual Studio 솔루션
│   ├── Framework/                   # D3D 렌더링 프레임워크
│   ├── Demo/                        # 데모 프로젝트
│   └── _Shaders/                    # HLSL 쉐이더 모음
│       ├── 00_Global.fx             # 전역 상수/구조체
│       ├── 00_Light.fx              # 라이팅 시스템
│       ├── 01_Line.fx ~ 02_LineColor.fx    # 기본 라인 렌더링
│       ├── 03_Pass.fx               # 렌더 패스
│       ├── 04_Plane.fx              # 평면 렌더링
│       ├── 05_World.fx              # 월드 변환
│       ├── 06_VertexID.fx           # VertexID 활용
│       ├── 07_Grid.fx               # 그리드 렌더링
│       ├── 08_Texture.fx            # 텍스처 매핑
│       ├── 09_SamplerState.fx       # 샘플러 스테이트
│       ├── 10_Terrain.fx            # 터레인 렌더링
│       ├── 11_DebugLine.fx          # 디버그 라인
│       ├── 12_Tri.fx                # 삼각형 렌더링
│       ├── 13_StaticMesh.fx         # 스태틱 메시
│       ├── 14_CubeMap.fx            # 큐브맵 환경 매핑
│       ├── 15_Sky.fx                # 스카이박스
│       ├── 16_SkeletalMesh.fx       # 스켈레탈 메시
│       ├── 17_Animation.fx          # 본 애니메이션
│       ├── 18_ByteAddress.fx        # ByteAddressBuffer
│       ├── 19_TextureBuffer.fx      # 텍스처 버퍼
│       └── 20_Canvas.fx             # 캔버스 렌더링
├── _Datas/                          # 데이터 리소스
├── _Libraries/                      # 외부 라이브러리
├── _Models/                         # 3D 모델 에셋
├── _Textures/                       # 텍스처 에셋
└── ShaderCompiler.exe               # 쉐이더 컴파일러
```

**핵심 구현 내용:**
- **D3D 렌더링 프레임워크** (Framework + Demo 구조)
- **HLSL 쉐이더 파이프라인** — 총 20+ 쉐이더 단계별 구현
  - 기본 도형 → 텍스처 → 라이팅 → 터레인 → 메시 → 스켈레탈 애니메이션
- **렌더링 기법:**
  - 텍스처 매핑 & 샘플러 스테이트
  - 라이팅 시스템 (Directional/Point/Spot Light)
  - 큐브맵 환경 매핑 & 스카이박스
  - 스켈레탈 메시 & 본 애니메이션 렌더링
  - ByteAddressBuffer / TextureBuffer 활용
- **커스텀 ShaderCompiler** 도구 포함

---

## 4. 기술 역량 요약 (Skills Summary)

### 🏗️ 아키텍처 & 설계
| 역량 | 상세 |
|------|------|
| **컴포넌트 기반 설계** | UE Actor-Component 패턴, 재사용 가능 모듈 설계 |
| **플러그인 아키텍처** | UE 에디터 플러그인 모듈 설계 (`IModuleInterface`) |
| **렌더링 파이프라인** | D3D 기반 커스텀 렌더링 프레임워크 구축 |

### 🎮 Unreal Engine C++
| 역량 | 적용 프로젝트 |
|------|-------------|
| UE C++ 기초 (UCLASS, UPROPERTY, UFUNCTION) | U04 |
| 캐릭터 시스템 (Character, Controller, Camera) | U05, U06, U07 |
| Gameplay Ability System (GAS) | U05, U07 |
| Online Subsystem (세션, 리플리케이션) | U06 |
| AI (Behavior Tree, AI Controller) | U07 |
| 에디터 확장 (Toolbar, Detail Panel, Asset Type) | U08 |
| GameplayDebugger 커스터마이징 | U08 |
| RHI 레이어 직접 접근 | U08 |
| Slate UI 프로그래밍 | U08 |
| 직렬화 (Binary Serialization) | U08 |

### 🖥️ 그래픽스 프로그래밍
| 역량 | 적용 프로젝트 |
|------|-------------|
| Direct3D 렌더링 파이프라인 | Tore09_D3D |
| HLSL 쉐이더 프로그래밍 (VS/PS) | Tore09_D3D |
| 라이팅 모델 구현 | Tore09_D3D |
| 스켈레탈 애니메이션 렌더링 | Tore09_D3D |
| 환경 매핑 (CubeMap, Skybox) | Tore09_D3D |
| 터레인 렌더링 | Tore09_D3D |
| GPU 버퍼 (ByteAddress, TextureBuffer) | Tore09_D3D |

---

## 5. 학습 로드맵 (Learning Roadmap)

```
2024.05 ──── U04_BasicSyntaxCPP ────── UE C++ 기초 문법
     │
2024.06 ──── U05_ThirdPersonCPP ────── 3인칭 캐릭터 + GAS-like 구현
     │
2024.07 ──── U06_OSS ──────────────── 온라인 서브시스템 (멀티플레이어)
     │
2024.08 ──── U07_GAS ──────────────── Gameplay Ability System 심화
     │
2024.09 ──── U08_Misc ─────────────── 에디터 플러그인 + RHI + 고급 기능
     │
2024.10 ──── Tore09_D3D ───────────── DirectX 3D 그래픽스 엔진
```

---

## 6. 빌드 및 실행 환경

| 항목 | 사양 |
|------|------|
| **IDE** | Visual Studio 2019+ |
| **언리얼 엔진** | UE4/UE5 (C++ 프로젝트) |
| **그래픽스 API** | DirectX 11 |
| **OS** | Windows 10/11 |
| **빌드 시스템** | UE Build Tool (`.Target.cs`, `.Build.cs`) / MSBuild (`.sln`, `.vcxproj`) |

---

---

## 영상

[1.기본적인 움직임과 숫자키로 무기 변경]https://github.com/user-attachments/assets/bfe77b60-601d-41d1-aab0-cf6439739b67

[2.위젯을 이용한 무기 변경]https://github.com/user-attachments/assets/e81c0c3d-aec9-40b4-88a9-731cb99a2395

[3.무기 시연 1]https://github.com/user-attachments/assets/983a4e1b-25c8-43c9-bfd9-354761c9a63b

[4.무기 시연 2]https://github.com/user-attachments/assets/ce96fae4-5a5c-4d74-a230-8b28f8eee824

[5.IK Component를 이용한 캐릭터 관절 표현]https://github.com/user-attachments/assets/518fbcf1-78c9-4e86-aa2e-8a0e27ab7a3d

---
