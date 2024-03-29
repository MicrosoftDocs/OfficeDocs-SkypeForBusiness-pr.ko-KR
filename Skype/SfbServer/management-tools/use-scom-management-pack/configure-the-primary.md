---
title: 기본 관리 서버를 구성하는 방법
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: '요약: 기본 관리 서버를 구성하고, System Center Operations Manager를 설치하고, 비즈니스용 Skype 서버 2015용 관리 팩을 가져오는 방법을 설명하는 문서입니다.'
ms.openlocfilehash: fe03f40f3fd63cf7bc88a8739c04dd98369be26f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398762"
---
# <a name="how-to-configure-the-primary-management-server"></a>기본 관리 서버를 구성하는 방법

**요약:** 기본 관리 서버를 구성하고, System Center Operations Manager를 설치하고, 비즈니스용 Skype 서버 2015용 관리 팩을 가져올 수 있습니다.

비즈니스용 Skype 서버 2015에 포함된 새로운 상태 모니터링 기능을 모두 활용하려면 먼저 기본 관리 서버로 사용할 컴퓨터를 지정해야 합니다. 그런 다음 해당 컴퓨터에 System Center Operations Manager 2012 SP1 또는 R2 또는 System Center Operations Manager 2007 R2를 설치해야 합니다. 또한 Operations Manager 백 엔드 데이터베이스로 작동하려면 먼저 지원되는 SQL Server 버전을 설치해야 합니다.

Operations Manager를 System Center 경우 다음을 포함하여 해당 제품의 모든 구성 요소를 설치해야 합니다.

- 운영 데이터베이스

- 서버

- 콘솔

- Windows PowerShell cmdlet

- 웹 콘솔

- 보고

- 데이터 웨어하우스

> [!IMPORTANT]
> Microsoft Report Viewer Operations Manager 2012를 설치하기 전에 System Center 패키지를 설치해야 합니다.

이러한 제품 및 설치에 대한 자세한 내용은 [System Center Operations Manager 2012를 참조합니다.](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))


배포당 루트 관리 서버는 하나만 비즈니스용 Skype 서버 있습니다.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>2015 비즈니스용 Skype 서버 팩 가져오기

관리 팩System Center Operations Manager에서 모니터링할 수 있는 항목System Center 해당 항목을 모니터링하는 방법 및 경고가 트리거 및 보고되는 방법을 표시하는 소프트웨어)를 설치하여 System Center Operations Manager의 기능을 확장할 수 있습니다. 비즈니스용 Skype 서버 2015에는 다음 기능을 제공하는 System Center Operations Manager 관리 팩 두 개가 포함되어 있습니다.

-  구성 요소 및 사용자 관리 팩(Microsoft.LS.2015.Monitoring.ComponentAndUser.mp)은 이벤트 비즈니스용 Skype 서버 기록되거나, 성능 카운터에 등록되거나, CDRS(통화 정보 기록) 또는 QoE(QoE) 데이터베이스에 기록된 문제를 추적합니다. 중요한 문제를 System Center 전자 메일, 인스턴트 메시지 또는 SMS 메시징을 통해 관리자에게 즉시 알리도록 Operations Manager를 구성할 수 있습니다. SMS(Short Message Service)는 모바일 장치에서 다른 모바일 장치로 문자 메시지를 보내는 데 사용되는 기술입니다.

    > [!NOTE]
    >  Operations Manager 알림 구성에 대한 자세한 내용은 [Configuring Notification을 참조합니다](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).

- **활성** 모니터링 관리 팩(Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp)은 시스템에 로그인하거나비즈니스용 Skype 서버 인스턴트 메시지를 변경하거나 PSTN(Public Switched Telephone Network)에 있는 전화로 전화를 걸기 등 주요 비즈니스용 Skype 서버 구성 요소를 사전 예방적으로 테스트합니다. 이러한 테스트는 가상 트랜잭션 cmdlet을 사용하여 비즈니스용 Skype 서버 수행됩니다. 예를 들어 **Test-CsIM** cmdlet은 한 쌍의 테스트 사용자 간의 인스턴트 메시징 대화를 시뮬레이션하는 데 사용됩니다. 이 시뮬레이트된 대화가 실패하면 경고가 생성됩니다.

관리 팩을 가져오는 것은 중요한 단계입니다. 관리 팩을 가져오지 않은 경우 Operations Manager를 사용하여 가상 트랜잭션을 모니터링하거나 비즈니스용 Skype 서버 실행할 비즈니스용 Skype 서버 없습니다.

구성 요소 및 사용자 관리 팩은 2015에서만 비즈니스용 Skype 서버 사용됩니다. 비즈니스용 Skype 서버 2015 및 Lync Server 2013이 모두 설치된 동시 사용 시나리오에서는 Lync Server 2013 컴퓨터에 Lync Server 2013 관리 팩을 계속 사용해야 합니다.

> [!NOTE]
> 비즈니스용 Skype 서버 2015용 관리 팩에는 비즈니스용 Skype 서버 2015 구성 요소 및 사용자 관리 팩과 비즈니스용 Skype 서버 2015 Active Monitoring Management Pack이 포함되어 있습니다.

다음 도구 중 하나를 사용해서 관리 팩을 가져올 수 있습니다.

- **System Center Operations Manager** 이 방법을 사용하면 Operations Manager를 사용하여 작업 관리자에 대한 모니터링을 비즈니스용 Skype 서버.

- **Operations Manager Shell** Operations Manager Shell Operations Manager 콘솔을 사용하여 관리 팩을 직접 가져오거나 관리 팩을 가져올 때 발생하는 문제를 System Center 있습니다.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Operations Manager를 사용하여 관리 팩 System Center 가져오기

1. Microsoft SkypeForBusiness2015ManagementPacks.msi 다운로드에서 앱을 다운로드하고 msi를 설치합니다.

2. 작업 System Center 관리자에서 관리 를 **클릭합니다**.

3. 관리 창에서 **관리 팩** 을 마우스 오른쪽 단추로 클릭한 후 **관리 팩 가져오기** 를 클릭합니다.

4. **관리 팩 선택** 대화 상자에서 **추가** 를 클릭한 후 **디스크에서 추가** 를 클릭합니다.

5. 온라인 **카탈로그 연결** 대화 상자에서 아니요를 **클릭합니다**.

6. 가져올 **관리 팩** 선택 대화 상자에서 파일을 찾아서 선택한 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 열기 를 **클릭합니다**. 대화 상자에서 여러 파일을 선택하려면 첫 번째 파일을 클릭한 다음 Ctrl 키를 잡고 후속 파일을 클릭합니다.

7. **관리 팩 선택** 대화 상자에서 **설치** 를 클릭합니다. 오류 메시지가 표시되고 설치가 실패하면 일반적으로 관리 팩 파일이 Windows 사용자 계정 컨트롤에서 보호되는 폴더에 있기 때문일 수 있습니다. 이 경우 파일을 다른 폴더에 복사한 다음 가져오기 및 설치 프로세스를 다시 시작합니다.

8. **관리 팩 선택** 대화 상자에서 **닫기** 를 클릭합니다. 가져오기 및 설치 프로세스를 완료하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>관리 팩을 사용하여 Operations Manager Shell

일반적으로 Operations Manager 콘솔을 사용하여 관리 팩을 가져오는 것이 더 쉽습니다. 그러나 오류가 발생하고 가져오기에 실패하면 콘솔에서 항상 적절한 오류 보고서를 제공하지는 않습니다. 이에 비해 이 Operations Manager Shell 자세한 정보를 제공합니다. Operations Manager를 사용하는 중 관리 팩을 가져올 때 문제가 발생하는 경우 이 팩을 사용하여 Operations Manager Shell. 사용자가 제공하는 Operations Manager Shell 가져오기 실패 이유를 확인하는 데 도움이 될 수 있습니다.

1. **시작,** **모든 프로그램**, **Microsoft System Center 2012**, **Operations Manager**, **Operations Manager Shell.**

2. 이 Operations Manager Shell 파일 복사본에 대한 실제 경로를 사용하여 명령 프롬프트에 다음 명령을 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp Enter를 누를 수 있습니다.

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. 첫 번째 관리 팩을 가져온 후 다음 파일 복사본에 대한 경로를 사용하여 프로세스를 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp.

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```