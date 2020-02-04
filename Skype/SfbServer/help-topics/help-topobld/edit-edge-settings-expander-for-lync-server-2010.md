---
title: Lync Server 2010용 Edge 설정 확장기 편집
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.EdgeSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74a66817-7092-4b2f-a2af-bc1a2c9e5fed
description: 다음 속성을 구성 하 여 Edge 서버 또는 Edge 풀에 대 한 설정을 편집 합니다.
ms.openlocfilehash: 78edbc8093b54474ac9f0429b5232851a5a16663
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697383"
---
# <a name="edit-edge-settings-expander-for-lync-server-2010"></a>Lync Server 2010용 Edge 설정 확장기 편집
 
다음 속성을 구성 하 여 Edge 서버 또는 Edge 풀에 대 한 설정을 편집 합니다. 
  
 **일반**
  
- **내부 풀 FQDN**: 내부 풀의 정규화 된 도메인 이름은 DNS (domain name system) 호스트 (A 또는 AAAA for IPv6) 레코드에 정의 된 edge 서버 또는 edge 풀의 id입니다.
    
- 다른 세션 초기화 프로토콜 파트너와의 페더레이션에 대 한 Edge 서버 또는 Edge 풀을 사용 하도록 설정 하려면 **이 edge 풀에 대해 페더레이션 사용 (포트 5061)** 을 선택 합니다.
    
    > [!IMPORTANT]
    > 오직 하나의 Edge 서버 또는 경계 풀만 페더레이션 용으로 정의할 수 있습니다. 연결 된 스크린샷에 표시 된 구성은 다른 Edge 서버 또는 경계 풀이 페더레이션에 대해 이미 구성 되었음을 나타냅니다. 페더레이션 (_sipfederationtls _tcp\< 에 대 한 외부 DNS SRV 레코드입니다. 외부 도메인 이름\>)이 페더레이션에 대 한 edge 서버 또는 edge 풀을 가리킵니다. 
  
- 기본적으로 TCP 포트 4443에서 **내부 구성 복제 포트 (HTTPS)** 는 중앙 관리 저장소의 로컬 (즉, 로컬) 서버 복사본을 복제 하는 포트입니다. 중앙 관리 저장소의 로컬 복사본은 각 컴퓨터의 SQL Server에 있는 **RTCLOCAL** 데이터베이스에 있습니다. 복제는 중앙 관리 서버 (중앙 관리 서버 역할을 보유 하는 프런트 엔드 서버 또는 프런트 엔드 풀)에서 Edge 서버에 대 한 단방향으로 시작 되며 내부 인터페이스 포트입니다.
    
  **다음 홉 선택**
  
- **다음 홉 풀**목록에 대해를 선택 합니다. 이 역할을 맡도록 디렉터, 디렉터 풀, 프런트 엔드 서버 또는 프런트 엔드 풀 중 하나를 정의 합니다. 다음 홉 풀은 Edge 서버 또는 Edge 풀 내부 인터페이스에서 인바운드 SIP 메시지를 받아 경계 내부 인터페이스에 아웃 바운드 SIP를 보내는 서버 또는 서버 풀입니다.
    
    > [!NOTE]
    > 디렉터는 선택적 역할 이며 디렉터를 배포 하지 않기로 결정 한 경우 프런트 엔드 서버 (단일 컴퓨터 또는 풀)가 디렉터 역할을 맡을 수 있습니다. 
  
  **외부 설정**
  
속성의이 섹션에서는 Edge 서버 또는 Edge 풀의 외부 설정에 대 한 속성을 편집할 수 있습니다. 편집할 수 있는 속성은 다음과 같습니다.
  
- 각 Edge 서버 서비스에 고유한 IP 주소와 정규화 된 도메인 이름을 할당 하려면 **웹 회의에 별도의 FQDN 및 IP 주소 사용** 확인란을 선택 합니다.
    
    > [!NOTE]
    > 확인란을 선택 하지 않도록 선택 하는 경우 각 Edge 서비스에 대해 별도의 포트를 사용 해야 합니다. 각 Edge 서비스는 액세스 경계 서비스에 대해 정의 된 FQDN을 공유 하므로 동일한 IP 주소를 사용 하 게 됩니다. 각 Edge 서비스는 고유한 IP 주소와 동일한 포트 또는 IP 주소와 고유 포트 값을 통해 고유 하 게 식별 되어야 합니다. 
  
- NAT (network address translation) 장치 뒤에서 숨겨지는 개인 주소 또는 기타 주소를 사용 하도록 A/V edge 서비스를 구성 하려면 **a/v edge 서비스** 를 선택 합니다.
    
- **액세스에 지 서비스**를 편집 하려면 호스트에 의해 DNS에 정의 된 액세스에 지 서비스에 대 한 **풀 FQDN** (A 및 IPv6이 사용 되는 경우 AAAA) 레코드 및 포트 값을 정의 합니다.
    
- **웹 회의에 지 서비스**를 편집 하려면 호스트에서 DNS에 정의한 웹 회의에 지 서비스에 대 한 **풀 FQDN** (a 및 IPv6이 사용 되는 경우 AAAA) 레코드 및 포트 값을 정의 합니다.
    
- **A/v edge 서비스**를 편집 하려면 호스트에서 DNS에 정의한 a/v edge 서비스에 대 한 **풀 FQDN** 을 정의 하 고 (a 및 IPv6이 사용 되는 경우 AAAA) 레코드 및 포트 값
    
    > [!IMPORTANT]
    > **웹 회의 및 A/V에 대해 별도의 FQDN 및 IP 주소 사용** 확인란을 선택한 경우에는 액세스에 지 서비스 풀 FQDN만 편집할 수 있습니다. 세 개의 Edge 서비스 각각에 대해 개별 포트를 할당 합니다.
  
  **확인**: 변경 내용을 적용하고 대화 상자로 커밋합니다.
  
  **취소**: 변경 내용을 취소하고 대화 상자를 닫습니다.
  
  **도움말**: 이 도움말 화면을 표시합니다.
  

