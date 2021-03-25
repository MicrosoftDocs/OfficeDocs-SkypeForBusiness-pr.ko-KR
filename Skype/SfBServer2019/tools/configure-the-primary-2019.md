---
title: 주요 관리 서버 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 기본 관리 서버를 구성하고, System Center Operations Manager를 설치하고, 비즈니스용 Skype 서버 2019용 관리 팩을 가져오는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: 02a174fb5c5fd6f06188553d8b2647c7162966e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120469"
---
# <a name="configure-the-primary-management-server"></a>주요 관리 서버 구성

**요약:** 기본 관리 서버를 구성하고, System Center Operations Manager를 설치하고, 비즈니스용 Skype 서버 2019용 관리 팩을 가져올 수 있습니다.

비즈니스용 Skype 서버 2019에 포함된 새로운 상태 모니터링 기능을 모두 활용하려면 먼저 기본 관리 서버로 사용할 컴퓨터를 지정해야 합니다. 그런 다음 해당 컴퓨터에 System Center Operations Manager 2012 SP1 또는 R2 또는 System Center Operations Manager 2007 R2를 설치해야 합니다. 또한 Operations Manager 백 엔드 데이터베이스로 작동하려면 먼저 지원되는 SQL Server 버전을 설치해야 합니다.

System Center Operations Manager를 설치할 때 다음을 포함하여 해당 제품의 모든 구성 요소를 설치해야 합니다.

- 운영 데이터베이스

- 서버

- 콘솔

- Windows PowerShell cmdlet

- 웹 콘솔

- 보고

- 데이터 웨어하우스

> [!IMPORTANT]
> System Center Operations Manager[2012를 설치하기 전에 "Microsoft Report Viewer 2010 재배포](https://www.microsoft.com/download/details.aspx?id=6442)가능한 패키지"를 설치해야 합니다.

이러한 제품 및 설치에 대한 자세한 내용은 다음 링크를 참조하세요.

- [System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

비즈니스용 Skype 서버 배포당 루트 관리 서버는 하나만 사용할 수 있습니다.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>비즈니스용 Skype 서버 2019 관리 팩 가져오기

System Center Operations Manager에서 모니터링할 수 있는 항목, 해당 항목을 모니터링하는 방법 및 경고가 트리거 및 보고되는 방법을 제어하는 소프트웨어인 관리 팩을 설치하여 System Center Operations Manager의 기능을 확장할 수 있습니다. 비즈니스용 Skype 서버 2019에는 다음 기능을 제공하는 두 가지 System Center Operations Manager 관리 팩이 포함되어 있습니다.

-  구성 요소 및 사용자 관리 팩(Microsoft.LS.2019.Monitoring.ComponentAndUser.mp)은 이벤트 로그에 기록되거나, 성능 카운터에 등록되거나, CDRS(통화 정보 기록) 또는 QoE(QoE) 데이터베이스에 기록된 비즈니스용 Skype 서버 문제를 추적합니다. 중요한 문제의 경우 전자 메일, 인스턴트 메시지 또는 SMS 메시징을 통해 관리자에게 즉시 알리도록 System Center Operations Manager를 구성할 수 있습니다. SMS(Short Message Service)는 모바일 장치에서 다른 모바일 장치로 문자 메시지를 보내는 데 사용되는 기술입니다.

    > [!NOTE]
    >  Operations Manager 알림을 구성하는 자세한 내용은 [Configuring Notification을 참조합니다.](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))

- **활성** 모니터링 관리 팩(Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp)은 시스템에 로그인하거나, 인스턴트 메시지를 변경하거나, PSTN(Public Switched Telephone Network)에 있는 전화로 전화를 걸기 등 주요 비즈니스용 Skype 서버 구성 요소를 사전 예방적으로 테스트합니다. 이러한 테스트는 비즈니스용 Skype 서버 가상 트랜잭션 cmdlet을 사용하여 수행됩니다. 예를 들어 **Test-CsIM** cmdlet은 한 쌍의 테스트 사용자 간의 인스턴트 메시징 대화를 시뮬레이션하는 데 사용됩니다. 이 시뮬레이트된 대화가 실패하면 경고가 생성됩니다.

관리 팩을 가져오는 것은 중요한 단계입니다. 관리 팩을 가져오지 않은 경우 Operations Manager를 사용하여 비즈니스용 Skype 서버 이벤트를 모니터링하거나 비즈니스용 Skype 서버 가상 트랜잭션을 실행할 수 없습니다.

구성 요소 및 사용자 관리 팩은 비즈니스용 Skype 서버 2019만 모니터링하는 데 사용됩니다. 비즈니스용 Skype 서버 2019 및 비즈니스용 Skype 서버 2015가 모두 설치된 동시 사용 시나리오인 경우 비즈니스용 Skype 서버 2015 컴퓨터에 대해 비즈니스용 Skype Server 2015 관리 팩을 계속 사용해야 합니다.

> [!NOTE]
> 비즈니스용 Skype 서버 2019 관리 팩에는 비즈니스용 Skype 서버 2019 구성 요소 및 사용자 관리 팩과 비즈니스용 Skype 서버 2019 활성 모니터링 관리 팩이 포함되어 있습니다.

다음 도구 중 하나를 사용해서 관리 팩을 가져올 수 있습니다.

- **System Center Operations Manager** 이 방법을 사용하면 Operations Manager를 사용하여 비즈니스용 Skype 서버에 대한 모니터링을 추가합니다.

- **Operations Manager 셸** Operations Manager 셸을 사용하여 직접 가져오거나 System Center Operations Manager 콘솔을 사용하여 관리 팩을 가져올 때 발생하는 문제를 해결할 수 있습니다.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager를 사용하여 관리 팩 가져오기

1. Microsoft SkypeForBusiness2019ManagementPacks.msi 다운로드에서 앱을 다운로드하고 msi를 설치합니다.

2. System Center Operations Manager에서 관리 를 **클릭합니다.**

3. 관리 창에서 **관리 팩** 을 마우스 오른쪽 단추로 클릭한 후 **관리 팩 가져오기** 를 클릭합니다.

4. **관리 팩 선택** 대화 상자에서 **추가** 를 클릭한 후 **디스크에서 추가** 를 클릭합니다.

5. 온라인 **카탈로그 연결 대화** 상자에서 아니요를 **클릭합니다.**

6. 가져올 **관리 팩** 선택 대화 상자에서 파일을 찾아서 선택한 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp Microsoft.LS.2019.Monitoring.ComponentAndUser.mp 열기 를 **클릭합니다.** 대화 상자에서 여러 파일을 선택하려면 첫 번째 파일을 클릭한 다음 Ctrl 키를 잡고 후속 파일을 클릭합니다.

7. **관리 팩 선택** 대화 상자에서 **설치** 를 클릭합니다. 오류 메시지가 표시되고 설치가 실패하면 일반적으로 관리 팩 파일이 Windows 사용자 계정 컨트롤에서 보호되는 폴더에 있기 때문일 수 있습니다. 이 경우 파일을 다른 폴더에 복사한 다음 가져오기 및 설치 프로세스를 다시 시작합니다.

8. **관리 팩 선택** 대화 상자에서 **닫기** 를 클릭합니다. 가져오기 및 설치 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager 셸을 사용하여 관리 팩 가져오기

일반적으로 Operations Manager 콘솔을 사용하여 관리 팩을 가져오는 것이 더 쉽습니다. 그러나 오류가 발생하고 가져오기에 실패하면 콘솔에서 항상 적절한 오류 보고서를 제공하지는 않습니다. 이에 비해 Operations Manager 셸은 자세한 정보를 제공합니다. Operations Manager를 사용하는 경우 관리 팩을 가져올 때 문제가 발생하는 경우 Operations Manager 셸을 사용하여 팩을 가져와야 합니다. Operations Manager 셸에서 제공하는 정보를 통해 가져오기 실패 이유를 확인할 수 있습니다.

1. **시작,** **모든** 프로그램, Microsoft System Center 2012, **Operations Manager,** **Operations Manager Shell을 클릭합니다.** 

2. Operations Manager Shell에서 파일 복사본에 대한 실제 경로를 사용하여 명령 프롬프트에 다음 명령을 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp Enter를 누를 수 있습니다.

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. 첫 번째 관리 팩을 가져온 후 다음 파일 복사본에 대한 경로를 사용하여 프로세스를 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp.

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```