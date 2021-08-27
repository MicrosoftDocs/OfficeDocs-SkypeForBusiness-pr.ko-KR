---
title: 통화 대기 응용 프로그램 설정 마이그레이션
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 통화 파킹 응용 프로그램 마이그레이션에는 레거시 설치에서 업로드된 사용자 지정 보류 음악 파일을 사용하여 비즈니스용 Skype 서버 2019 풀을 프로비전하고, 서비스 수준 설정을 복원하고, 모든 통화 파킹된 통화 통화를 비즈니스용 Skype 서버 2019 풀로 다시 지정하는 것이 포함됩니다. 사용자 지정된 보류 음악 파일이 풀에 구성된 경우 이러한 파일을 새 2019 풀에 비즈니스용 Skype 서버 합니다. 또한 통화 파크에 대해 업로드된 사용자 지정된 보류 음악 파일의 별도의 백업 복사본을 보관하려면 통화 파크 사용자 지정 음악 통화음 파일을 다른 대상으로 백업하는 것이 좋습니다. 통화 파크 응용 프로그램에 대한 사용자 지정된 보류 음악 파일은 풀의 파일 저장소에 저장됩니다. 풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소로 복사하려면 다음 매개 변수와 함께 Xcopy 명령을 사용합니다.
ms.openlocfilehash: b8d2c5a898ca9ce4c2c1e8be4b9cbf3e7355a8cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597542"
---
# <a name="migrate-call-park-application-settings"></a>통화 대기 응용 프로그램 설정 마이그레이션

통화 파킹 응용 프로그램 마이그레이션에는 레거시 설치에서 업로드된 사용자 지정 통화 중 음악 파일을 사용하여 비즈니스용 Skype 서버 2019 풀을 프로비전하고 서비스 수준 설정을 복원하고 모든 통화 파킹된 통화 통화를 비즈니스용 Skype 서버 2019 풀로 다시 지정하는 것이 포함됩니다. 사용자 지정된 보류 음악 파일이 풀에 구성된 경우 이러한 파일을 새 2019 풀에 비즈니스용 Skype 서버 합니다. 또한 통화 파크에 대해 업로드된 사용자 지정된 보류 음악 파일의 별도의 백업 복사본을 보관하려면 통화 파크 사용자 지정 음악 통화 중 음악 파일을 다른 대상에 백업하는 것이 좋습니다. 통화 파크 응용 프로그램에 대한 사용자 지정된 보류 음악 파일은 풀의 파일 저장소에 저장됩니다. 풀 파일 저장소의 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소로 복사하려면 다음 매개 변수와 **함께 Xcopy** 명령을 사용합니다. 

```console
Xcopy <Source: legacy Pool CPS File Store Path> <Destination: Skype for Business Server 2019 Pool CPS File Store Path>
```

```console
Example usage:  Xcopy "<legacy File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Skype for Business Server 2019 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 
```

사용자 지정된 모든 오디오 파일을 비즈니스용 Skype 서버 2019 파일 저장소에 복사한 경우 비즈니스용 Skype 서버 2019 풀의 통화 파크 응용 프로그램 설정을 구성해야 합니다. 레거시 풀과 연결된 통화 파기 파선 범위를 비즈니스용 Skype 서버 2019 풀에 다시 지정해야 합니다.

통화 파킹 응용 프로그램 설정에는 선택 시간 제한 임계값, 통화 보류 음악을 사용 또는 사용 안 하게 설정, 최대 통화 선택 시도 및 시간 제한 요청이 포함됩니다. **Set-CsCpsConfiguration** cmdlet을 실행하려면 비즈니스용 Skype 서버 관리 셸을 사용하여 통화 파킹 응용 프로그램 설정을 관리해야 합니다. 제어판을 사용하여 통화 파크 응용 프로그램 설정을 관리할 비즈니스용 Skype 서버 없습니다. 

## <a name="reconfigure-the-call-park-service-settings"></a>통화 파기 서비스 서비스 구성 설정

1. 비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 비즈니스용 Skype 서버 셸을 여는 것입니다.

2. 명령줄에 다음을 입력합니다.

    > [!NOTE]
    > 2019 통화 비즈니스용 Skype 서버 설정이 레거시 설정과 동일한 경우 이 단계를 건너뛸 수 있습니다. 통화 파킹 응용 프로그램 설정이 비즈니스용 Skype 서버 2019 및 레거시 환경과 다른 경우 아래 cmdlet을 템플릿으로 사용하여 해당 변경 내용을 업데이트합니다. 

   ```PowerShell
   Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"
   ```

레거시 풀에서 비즈니스용 Skype 서버 2019 풀로 모든 통화 파크 파운데이트 범위를 다시 배정하기 위해 비즈니스용 Skype 서버 제어판 또는 비즈니스용 Skype 서버 관리 셸을 사용할 수 있습니다. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-control-panel"></a>제어판을 사용하여 모든 통화 비즈니스용 Skype 서버 다시 배정

1. 제어판을 비즈니스용 Skype 서버 를 니다.

2. 왼쪽 창에서 음성 기능을 **선택합니다.**

3. 통화 **파크 탭을** 선택합니다. 

4. 레거시 풀에 할당된 각 통화 파크 파랑 파선 범위에 대해 대상 서버의 **FQDN** 설정을 편집하고 통화 파크 요청을 비즈니스용 Skype 서버 2019 풀을 선택합니다. 

5. **커밋을** 선택하여 변경 내용을 저장합니다. 

## <a name="reassign-all-call-park-orbit-ranges-using-skype-for-business-server-management-shell"></a>관리 셸을 사용하여 모든 통화 비즈니스용 Skype 서버 다시 배정

1. 관리 비즈니스용 Skype 서버 셸을 열 수 있습니다.

2. 명령줄에 다음을 입력합니다.

   ```PowerShell
   Get-CsCallParkOrbit
   ```

    이 cmdlet은 배포의 모든 통화 파킹된 통화 수 범위를 나열합니다. **CallParkServiceId** 및 **CallParkServerFqdn** 매개 변수가 레거시 풀로 설정된 모든 통화 파킹된 통화 파킹된 통화 통화를 다시 배정해야 합니다. 

    레거시 통화 파크 궤도 범위를 비즈니스용 Skype 서버 2019 풀에 다시 배정하기 위해 명령줄에 다음을 입력합니다.

   ```PowerShell
   Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Skype for Business Server 2019 Pool FQDN>"
   ```

모든 통화 파킹된 통화선 범위를 비즈니스용 Skype 서버 2019 풀로 다시 배정하면 통화 파킹 응용 프로그램에 대한 마이그레이션 프로세스가 완료되어 비즈니스용 Skype 서버 2019 풀에서 이후의 모든 통화 파킹 요청을 처리합니다.


