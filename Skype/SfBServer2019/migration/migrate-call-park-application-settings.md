---
title: 통화 대기 응용 프로그램 설정 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 통화 대기 응용 프로그램의 마이그레이션에는 비즈니스용 Skype 서버 2019 풀을 레거시 설치에 업로드 된 보류 파일에 있는 사용자 지정 음악으로 프로 비전 하 고, 서비스 수준 설정을 복원 하 고, 모든 통화 공원 orbits 비즈니스용 Skype 서버 2019 풀. 사용자 지정 된 음악 보관 파일을 풀에서 구성한 경우 이러한 파일을 새 비즈니스용 Skype Server 2019 풀에 복사 해야 합니다. 또한 통화 대기를 위해 업로드 된 사용자 지정 음악 보관 파일에 대 한 별도의 백업 복사본을 유지 하기 위해 모든 통화 공원 사용자 지정 된 음악 파일을 다른 대상에 백업 하는 것이 좋습니다. 통화 공원 응용 프로그램에 대해 사용자 지정 된 음악 보관 파일은 풀의 파일 저장소에 저장 됩니다. 풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사 하려면 다음 매개 변수와 함께 Xcopy 명령을 사용 합니다.
ms.openlocfilehash: 0435144fc647a08d8252f35d8449d1e7daa62d68
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991163"
---
# <a name="migrate-call-park-application-settings"></a>통화 대기 응용 프로그램 설정 마이그레이션

통화 공원 응용 프로그램 마이그레이션에는 레거시 설치에 업로드 된 사용자 지정 음악 보관 파일과 함께 비즈니스용 Skype 서버 2019 풀 프로비저닝이 포함 되며, 서비스 수준 설정을 복원 하 고, 모든 통화 대기 orbits을 다시 지정 합니다. 비즈니스용 Skype 서버 2019 풀로 이동할 수 있습니다. 사용자 지정 된 음악 보관 파일을 풀에서 구성한 경우 이러한 파일을 새 비즈니스용 Skype Server 2019 풀에 복사 해야 합니다. 또한, 통화 대기를 위해 업로드 된 사용자 지정 음악 보관 파일의 별도 백업 복사본을 유지 하기 위해 모든 통화 공원 사용자 지정 된 음악 파일을 다른 대상에 백업 하는 것이 좋습니다. 통화 공원 응용 프로그램에 대해 사용자 지정 된 음악 보관 파일은 풀의 파일 저장소에 저장 됩니다. 풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사 하려면 다음 매개 변수와 함께 **Xcopy** 명령을 사용 합니다. 

```
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

사용자 지정 된 모든 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사한 경우 비즈니스용 Skype Server 2019 풀의 통화 공원 응용 프로그램 설정을 구성 하 고 레거시 풀과 연결 된 통화 공원 궤도 범위를 사용 해야 합니다. 비즈니스용 Skype 서버 2019 풀에 다시 할당 해야 합니다.

통화 공원 응용 프로그램 설정에는 픽업 시간 제한 임계값, 보류 중인 음악을 활성화 또는 비활성화, 최대 통화 픽업 시도 횟수, 제한 시간 요청이 포함 됩니다. **CsCpsConfiguration** cmdlet을 실행 하려면 비즈니스용 Skype Server Management Shell을 사용 하 여 통화 공원 응용 프로그램 설정을 관리 해야 합니다. 비즈니스용 Skype 서버 제어판을 사용 하 여 통화 공원 응용 프로그램 설정을 관리할 수 없습니다. 

## <a name="reconfigure-the-call-park-service-settings"></a>통화 공원 서비스 설정 다시 구성

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 셸을 엽니다.

2. 명령줄에 다음을 입력 합니다.

    > [!NOTE]
    > 비즈니스용 Skype 서버 2019 통화 공원 응용 프로그램 설정이 레거시 설정과 동일한 경우이 단계를 건너뛸 수 있습니다. 통화 공원 응용 프로그램 설정이 비즈니스용 Skype 서버 2019 및 레거시 환경과 다르면 아래 cmdlet을 서식 파일로 사용 하 여 해당 변경 내용을 업데이트 합니다. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

레거시 풀의 모든 통화 공원 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 하려면 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용할 수 있습니다. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>비즈니스용 Skype Server 제어판을 사용 하 여 모든 통화 공원 궤도 범위 다시 할당

1. 비즈니스용 Skype Server 제어판을 엽니다.

2. 왼쪽 창에서 **음성 기능**을 선택 합니다.

3. **통화 공원** 탭을 선택 합니다. 

4. 레거시 풀에 할당 된 각 통화 대기 궤도 범위에 대해 **대상 서버 설정의 FQDN** 을 편집 하 고 통화 공원 요청을 처리 하는 비즈니스용 Skype server 2019 풀을 선택 합니다. 

5. **커밋을** 선택 하 여 변경 내용을 저장 합니다. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>비즈니스용 Skype Server Management Shell을 사용 하 여 모든 통화 공원 궤도 범위 다시 할당

1. 비즈니스용 Skype 서버 관리 셸을 엽니다.

2. 명령줄에 다음을 입력 합니다.

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    이 cmdlet은 배포의 모든 통화 공원 궤도 범위를 나열 합니다. **CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수를 레거시 풀로 설정 하는 모든 통화 대기 orbits을 다시 할당 해야 합니다. 

    레거시 통화 공원 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 하려면 명령줄에 다음을 입력 합니다.

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

모든 통화 공원 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 할당 한 후에는 통화 대기 응용 프로그램에 대 한 마이그레이션 프로세스가 완료 되 고 비즈니스용 Skype 서버 2019 풀에서 이후의 모든 통화 대기 요청이 처리 됩니다.


