---
title: 주 관리 서버 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: '요약: 비즈니스용 Skype Server 2015에 대 한 기본 관리 서버를 구성 하 고 System Center Operations Manager를 설치 하 고 관리 팩을 가져옵니다.'
ms.openlocfilehash: a89ee8ca7c7f5601d9219ef49643adc2ebf99883
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187944"
---
# <a name="configure-the-primary-management-server"></a>주 관리 서버 구성

**요약:** 주 관리 서버를 구성 하 고 System Center Operations Manager를 설치 하 고 비즈니스용 Skype 서버 2015에 대 한 관리 팩을 가져옵니다.

비즈니스용 Skype 서버 2015에 포함 된 새로운 상태 모니터링 기능을 최대한 활용 하려면 먼저 기본 관리 서버로 작동할 컴퓨터를 지정 해야 합니다. 그런 다음 해당 컴퓨터에 System Center Operations Manager 2012 SP1 또는 R2 또는 System Center Operations Manager 2007 R2를 설치 해야 합니다. 또한, 먼저 Operations Manager 백 엔드 데이터베이스로 작동 하도록 지원 되는 SQL Server 버전을 설치 해야 합니다.

System Center Operations Manager를 설치 하는 경우 다음을 포함 하 여 해당 제품의 모든 구성 요소를 설치 해야 합니다.

- 운영 데이터베이스

- Server

- 콘솔

- Windows PowerShell cmdlet

- 웹 콘솔

- 보고

- 데이터 웨어하우스

> [!IMPORTANT]
> System Center Operations Manager 2012를 설치 하려면 먼저 "[Microsoft Report Viewer 2010 재배포 가능 패키지](https://www.microsoft.com/en-us/download/details.aspx?id=6442)"를 설치 해야 합니다.

이러한 제품과 설치에 대 한 자세한 내용은 다음 링크를 참조 하세요.

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

비즈니스용 Skype 서버 배포 당 하나의 루트 관리 서버만을 사용할 수 있습니다.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>비즈니스용 Skype 서버 2015 관리 팩 가져오기

관리 팩을 설치 하 여 system center operations Manager에서 모니터링할 수 있는 항목을 지정 하는 소프트웨어, 해당 항목을 모니터링 하는 방법, 알림을 트리거하는 방법 등 시스템 센터 Operations Manager의 기능을 확장할 수 있습니다. 보고. 비즈니스용 Skype 서버 2015에는 다음 기능을 제공 하는 두 가지 System Center Operations Manager 관리 팩이 포함 됩니다.

- **구성 요소 및 사용자 관리 팩** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) 이벤트 로그에 기록 되거나, 성능 카운터에 등록 되어 있거나, CDRs (통화 정보 레코드) 또는 체감 품질 (환경 품질) 데이터베이스에 기록 된 비즈니스용 Skype 서버 문제를 추적 합니다. 중요 한 문제의 경우 관리자에 게 전자 메일, 인스턴트 메시지 또는 SMS 메시지를 즉시 알리기 위해 System Center Operations Manager를 구성할 수 있습니다. (SMS 또는 짧은 메시지 서비스는 모바일 장치 간에 문자 메시지를 전송 하는 데 사용 되는 기술입니다.)

    > [!NOTE]
    >  Operations Manager 알림을 구성 하는 방법에 대 한 자세한 내용은 [알림 구성을](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)참조 하세요.

- **활성 모니터링 관리 팩** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) 사전 테스트 주요 비즈니스용 Skype 서버 구성 요소 (예: 시스템에 로그인, 인스턴트 메시지 교환 또는 PSTN (공공 교환 전화 네트워크)에 있는 휴대폰으로 전화 걸기) ). 이러한 테스트는 비즈니스용 Skype 서버 가상 트랜잭션 cmdlet을 사용 하 여 수행 됩니다. 예를 들어 **test-CsIM** cmdlet은 한 쌍의 테스트 사용자 간에 인스턴트 메시징 대화를 시뮬레이트하는 데 사용 됩니다. 이 시뮬레이트된 대화에 실패 하면 경고가 생성 됩니다.

관리 팩 가져오기는 매우 중요 한 단계입니다. 관리 팩을 가져오지 않으면 Operations Manager를 사용 하 여 비즈니스용 Skype Server 이벤트를 모니터링 하거나 비즈니스용 Skype 서버 가상 트랜잭션을 실행할 수 없습니다.

구성 요소 및 사용자 관리 팩은 비즈니스용 Skype 서버 2015만 모니터링 하는 데 사용 됩니다. 비즈니스용 Skype 서버 2015와 Lync Server 2013이 모두 설치 되어 있는 공존 시나리오를 사용 하는 경우에는 Lync Server 2013 컴퓨터에 대 한 Lync Server 2013 관리 팩을 계속 사용할 수 있습니다.

> [!NOTE]
> 비즈니스용 Skype server 2015의 관리 팩에는 비즈니스용 Skype 서버 2015 구성 요소와 사용자 관리 팩 및 비즈니스용 Skype 서버 2015 액티브 모니터링 관리 팩이 포함 됩니다.

다음 도구 중 하나를 사용 하 여 관리 팩을 가져올 수 있습니다.

- **System Center Operations Manager** 이 방법을 사용 하는 경우 Operations Manager를 사용 하 여 비즈니스용 Skype Server에 대 한 모니터링을 추가 합니다.

- **Operations Manager Shell** Operations Manager Shell을 사용 하 여 직접 가져오거나 System Center Operations Manager 콘솔을 사용 하 여 관리 팩을 가져올 때 발생 하는 문제를 해결할 수 있습니다.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>System Center Operations Manager를 사용 하 여 관리 팩 가져오기

1. Microsoft 웹 다운로드에서 SkypeForBusiness2015ManagementPacks를 다운로드 하 고 msi를 설치 합니다.

2. System Center Operations Manager에서 **관리**를 클릭 합니다.

3. 관리 창에서 **관리 팩**을 마우스 오른쪽 단추로 클릭 한 다음 **관리 팩 가져오기를**클릭 합니다.

4. **관리 팩 선택** 대화 상자에서 **추가**를 클릭 한 다음 **디스크에서 추가**를 클릭 합니다.

5. **온라인 카탈로그 연결** 대화 상자에서 **아니요**를 클릭 합니다.

6. **가져올 관리 팩 선택** 대화 상자에서 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 및 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 파일을 찾아 선택한 다음 **열기**를 클릭 합니다. 대화 상자에서 여러 파일을 선택 하려면 첫 번째 파일을 클릭 한 다음 Ctrl 키를 누른 채 후속 파일을 클릭 합니다.

7. **관리 팩 선택** 대화 상자에서 **설치**를 클릭 합니다. 오류 메시지가 표시 되 고 설치가 실패 하는 경우 일반적으로 관리 팩 파일이 Windows 사용자 계정 컨트롤에서 보호 하는 폴더에 있음을 의미 합니다. 이 문제가 발생 하면 파일을 다른 폴더에 복사한 다음 가져오기 및 설치 프로세스를 다시 시작 합니다.

8. **관리 팩 선택** 대화 상자에서 **닫기를**클릭 합니다. 가져오기 및 설치 프로세스를 완료 하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Operations Manager Shell을 사용 하 여 관리 팩 가져오기

일반적으로 Operations Manager 콘솔을 사용 하 여 관리 팩을 가져오는 것이 더 쉽습니다. 그러나 오류가 발생 하 고 가져오기에 실패 하는 경우 콘솔은 항상 적절 한 오류 보고서를 제공 하지 않습니다. 비교를 통해 Operations Manager 셸은 자세한 정보를 제공 합니다. Operations Manager를 사용 하는 경우 관리 팩을 가져올 때 문제가 발생 하면 Operations Manager Shell을 사용 하 여 팩을 가져옵니다. Operations Manager 셸이 제공 하는 정보를 통해 가져오기에 실패 한 이유를 확인할 수 있습니다.

1. **시작**, **모든 프로그램**, **Microsoft System Center 2012**을 클릭 하 고 **Operations Manager**를 클릭 한 다음 **operations manager Shell**을 클릭 합니다.

2. Operations Manager 셸에서 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 파일의 실제 경로를 사용 하 여 명령 프롬프트에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. 첫 번째 관리 팩을 가져온 후에는 파일 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp의 복사본 경로를 사용 하 여 프로세스를 반복 합니다.

   ```
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
