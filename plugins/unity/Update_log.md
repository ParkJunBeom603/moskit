# Update infomation (Unity plugin v0.23.00, 210104)

- v0.22.10 버전이 Unity 2019 버전 프로젝트를 빌드하고 .exe 파일을 실행할 때 정상 동작하지 않는 문제가 있어 Plugin을 두 버전으로 나누었습니다.
- 나누는 기준은 Unity 프로젝트의 .NET 버전 기준이며, 프로젝트의 .NET 버전 확인 방법은 아래와 같습니다.
- Unity 2018 일 때, Player Settings - Other Settings - Configuration - Scripting Runtime Version(기본값 : .NET 4.x Equivalent)
- Unity 2019 일 때, Player Settings - Other Settings - Configuration - Api Compatibility Level(기본값 : .NET Standard 2.0)
  
- Moskitpackage v0.23.00_2018.unitypackage
- 위 버전은 Unity 2018 이전 버전까지 쓰였던 플러그인입니다. 구체적으로는 프로젝트의 .NET 버전이 3.5인 프로젝트를 위한 플러그인입니다.

- Moskitpackage v0.23.00_2019.unitypackage
- 위 버전은 Unity 2019 이후 버전에서 쓰일 새 플러그인입니다. 구체적으로는 프로젝트의 .NET 버전이 4.x 또는 .NET Standard 2.0 인 프로젝트를 위한 플러그인입니다.
  
# Bug fix (Unity plugin v0.22.10, 201109)

- 추출된 영상 파일명이 디버그용 문자열로 고정된 문제를 수정하였습니다.

# Update infomation (Unity plugin v0.22.9, 201105)

- Windows Vista 이하 버전 지원이 종료되었습니다.

# Bug fix (Unity plugin v0.22.9, 201105)

- Windows Vista 이상일 때, Unity Editor 창이 최대화 상태면 avi 파일 추출이 안되는 문제를 수정하였습니다.

# Update infomation (Unity plugin v0.22.8, 200803)

- Unity 2019.4.6f1 버전에서 정상 동작되는 것을 확인하였습니다.

# Bug fix (Unity plugin v0.22.7, 191218)

- Unity 2018 이후 버전의 안드로이드 플랫폼에서 bin 파일이 추출되지 않던 문제를 수정하였습니다.

# Update infomation (Unity plugin v0.22.6, 191105)

- MSPlugin 프리팹에 모스킷 컴포넌트가 깨져있던 것을 수정하였습니다.

# Update infomation (Unity plugin v0.22.5, 190314)

- 낮은 버전의 유니티에서도 Moskit이 동작하도록 하였습니다.(Unity 5.3.0f4까지 정상 동작함을 확인)

# Update infomation (Unity plugin v0.22.4, 190307)

- 추출하는 정보에 플랫폼 정보(Windows, Mobile 등)가 추가되었습니다.

# Update infomation (Unity plugin v0.22.3, 190116)

- 예외상황 발생시 예외상황을 기록한 파일과 덤프 파일이 생성됩니다.

# Bug fix (Unity plugin v0.22.2, 190111)

- Object에 정상적이지 않은 Component가 있을때 bin 파일이 정상적으로 만들어지지 않는 현상이 수정되었습니다.

# Update infomation (Unity plugin v0.22.2, 190111)

- 매개변수 isMoskitStartWithUnity가 추가되었습니다.

- 매개변수명이 수정되었습니다.

# Bug fix (Unity plugin v0.22.1, 181129)

- AndroidOS에서  bin 파일이 정상적으로 만들어지지 않는 현상이 수정되었습니다.

- 녹화프로그램 경로가 비정상적이였던 부분이 수정되었습니다.

- Scene이 넘어갈 때 MainCamera를 잡지 못하는 현상을 수정하였습니다.

# Update infomation (Unity plugin v0.22.1, 181129)

- Video녹화 OnOff 추가

- 카메라를 Plugin 내부에서 찾게 변경

- DontDestroyOnLoad gameObject로 변경

## 사용 방법 (Moskit UnityPlugin)

1. 인스펙터의 각 매개변수 설정
	
	* > fFloorToCameraHeight : 월드에 배치된 카메라와 바닥의 높이 차이

	* > strOutputFilePath : 데이터 (.bin)파일과 영상(.avi)파일이 출력될 경로

	* > ScaleRatio : 컨텐츠의 축척비율 (축척비, default (Unity) . 1unit == 1m)

	* > isActive : Plugin ON/OFF기능	

	* > isWithVideo : Plugin의 녹화ON/OFF기능 ( Multiple Display Streaming환경에서는 녹화 기능이 원할하지 않을 수 있습니다. )

	* > isConnectedToHardware : VR컨텐츠에 이용되는 하드웨어의 자이로센서값을 받아올 때 사용하는 변수

	* > isConnectingLog : hardware 연결 상태 로그 출력용 변수 (true 시 Log출력)
	
	* > isMoskitStartWithUnity : true일때는, 유니티 시작과 동시에 Moskit이 데이터를 생성합니다. 
	false일때는, 별도로 Moskit의 시작과 종료를 전환해줄 필요가 있습니다.
	

2. Scene의 시작부분에 하나만 배치합니다. ( DontDestroyOnLoad )

3. 콘텐츠가 종료되지 않는 프로그램이라면, 추가 작업이 필요합니다.

	* > MSPlugin 오브젝트의 MoskitPluginMain Component의 moskit_state변수를 콘텐츠가 끝나는 시점에 'End'로 설정해주세요.

## 주의 사항	

1. 각 매개변수를 설정하지 않으면 데이터 파일 처리가 원활히 이루어지지 않아 분석에 문제가 생길 수 있습니다.
 
## 기타

# update infomation (Unity plugin v0.22)

- 사용 방법 변경 

- Hardware 연결기능 추가
