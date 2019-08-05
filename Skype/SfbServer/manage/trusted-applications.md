---
title: 신뢰할 수 있는 응용 프로그램 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 MA) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.
ms.openlocfilehash: 272785cd1dcfe0bf21f7ac2b5ab64f36646237eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187074"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 신뢰할 수 있는 응용 프로그램 관리

*신뢰할 수 있는 응용* 프로그램은 비즈니스용 Skype 서버에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 ma) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다. (C) MA 응용 프로그램에 대 한 자세한 내용은에서 http://go.microsoft.com/fwlink/p/?linkId=210320"통합 커뮤니케이션 관리 API 3.0 Core SDK 설명서"를 참조 하세요.

서버 역할을 추가 하거나 제거할 때 토폴로지를 성공적으로 게시, 사용 또는 사용 하지 않도록 설정 하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원 인 사용자로 로그온 해야 합니다. 

신뢰할 수 있는 새 응용 프로그램 서버를 구성 하 고 신뢰할 수 있는 응용 프로그램 목록을 보고 신뢰할 수 있는 응용 프로그램 정보를 보는 방법에 대해 알아보려면이 문서를 사용 하세요. 

## <a name="configure-a-new-trusted-application-server"></a>신뢰할 수 있는 새 응용 프로그램 서버 구성

1.  도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.

2.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버**를 차례로 클릭 한 다음 비즈니스용 **skype server 토폴로지 작성기**를 클릭 합니다.

3.  **기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.

4.  **다른 이름으로 토폴로지 저장** 대화 상자에서 사용할 토폴로지 작성기 파일을 클릭 한 다음 **저장**을 클릭 합니다.

5.  왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.

6.  신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고,이를 단일 서버 또는 다중 서버 중에서 선택 하 고 **다음**을 클릭 합니다.

7.  **다음 홉 선택** 페이지의 목록에서 비즈니스용 Skype 서버 프런트 엔드 풀을 선택 합니다.

8.  **마침을**클릭 합니다.

9.  최상위 노드 **비즈니스용 Skype 서버**를 선택 하 고 **작업** 메뉴에서 **토폴로지 게시**를 클릭 합니다.
    
    **신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어지고 올바른 프런트 엔드 풀에 연결 되어 있어야 합니다.


## <a name="view-a-list-of-trusted-applications"></a>신뢰할 수 있는 응용 프로그램 목록 보기

비즈니스용 skype server 제어판을 사용 하 여 비즈니스용 Skype 서버 환경에서 배포한 신뢰할 수 있는 응용 프로그램 목록을 볼 수 있습니다. 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 신뢰 하는 Microsoft 통합 커뮤니케이션 관리 API (인스턴스 MA) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다. 이 신뢰 관계는 다음 목록에 요약 되어 있습니다.

  - 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버 인증에 문제가 되지 않습니다.

  - 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 SIP 거래, 연결 또는 VoIP (인터넷 프로토콜) 전화를 위해 제한 되지 않습니다.

  - 신뢰 하는 응용 프로그램은 모든 사용자를 가장할 수 있으며 rosters에 표시 하지 않고 회의에 참가할 수 있습니다.

  - 신뢰할 수 있는 응용 프로그램은 가용성이 높고 탄력적입니다.

비즈니스용 Skype Server 제어판에는 응용 프로그램 이름, 실행 중인 풀, 사용 하는 포트 등이 표시 됩니다.


### <a name="to-view-a-list-of-trusted-applications"></a>신뢰할 수 있는 응용 프로그램 목록 보기

1.  CsServerAdministrator, CsAdministrator, CsHelpDesk 또는 Csserveradministrator 관리자 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다. 비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의 된 관리 역할에 대 한 자세한 내용은 [RBAC (역할 기반 액세스 제어](../plan-your-deployment/security/role-based-access-control-rbac.md))를 참조 하세요.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3.  왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 **신뢰할 수 있는 응용 프로그램**을 클릭 합니다.

4.  필요한 경우 **신뢰할 수 있는 응용 프로그램** 페이지에서 열 머리글을 클릭 하 여 응용 프로그램을 정렬 합니다.


## <a name="view-trusted-application-information"></a>신뢰할 수 있는 응용 프로그램 정보 보기

Windows PowerShell 및 **CsTrustedApplication** cmdlet을 사용 하 여 신뢰 된 응용 프로그램에 대 한 정보를 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 


### <a name="to-view-trusted-applications"></a>신뢰할 수 있는 응용 프로그램을 보려면

신뢰할 수 있는 모든 응용 프로그램을 보려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsConferenceDisclaimer
    
   이 명령은 각 신뢰 하는 응용 프로그램에 대해 다음과 같은 정보를 반환 합니다.
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
   자세한 내용은 [Get-help CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)을 참조 하세요.
