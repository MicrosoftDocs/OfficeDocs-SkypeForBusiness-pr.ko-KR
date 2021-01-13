---
title: 신뢰할 수 있는 응용 프로그램 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 신뢰하는 Microsoft UCMA(Unified Communications Managed API) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다.
ms.openlocfilehash: e9d29371014d902bbee38e2f3871c5579634c0f9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826278"
---
# <a name="manage-trusted-applications-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 신뢰할 수 있는 응용 프로그램 관리

신뢰할 수 있는 *응용* 프로그램은 비즈니스용 Skype 서버에서 신뢰하는 Microsoft UCMA(Unified Communications Managed API) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다. UCMA 응용 프로그램에 대한 자세한 내용은 "Unified Communications Managed API 3.0 Core SDK 설명서"를 https://go.microsoft.com/fwlink/p/?linkId=210320 참조하십시오.

서버 역할을 추가하거나 제거할 때 토폴로지를 게시, 사용하도록 설정 또는 사용하지 않도록 설정하려면 RTCUniversalServerAdmins 및 Domain Admins 그룹의 구성원인 사용자로 로그온해야 합니다. 

이 문서를 사용하여 신뢰할 수 있는 새 응용 프로그램 서버를 구성하고, 신뢰할 수 있는 응용 프로그램 목록을 보고, 신뢰할 수 있는 응용 프로그램 정보를 보는 방법을 배울 수 있습니다. 

## <a name="configure-a-new-trusted-application-server"></a>새 신뢰할 수 있는 응용 프로그램 서버 구성

1.  토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.

2.  토폴로지 작성기 **시작:** **시작,** 모든 **프로그램,** 비즈니스용 **Skype 서버,** 비즈니스용 Skype 서버 토폴로지 작성기 클릭

3.  **기존 배포에서 토폴로지 다운로드** 및 **확인** 을 차례로 클릭합니다.

4.  **토폴로지 저장** 대화 상자에서 사용할 토폴로지 작성기 파일을 클릭한 다음 저장을 **클릭합니다.**

5.  왼쪽 창에서 신뢰할 수 있는 응용 프로그램 서버를 마우스 오른쪽 단추로 클릭한 다음 새 신뢰할 수 있는 응용 **프로그램 풀을 클릭합니다.**

6.  신뢰할 수 있는 응용 프로그램 풀에 대한 **풀 FQDN** 을 입력하고 단일 서버로 설정할지 다중 서버로 설정할지 여부를 선택한 후 **다음** 을 클릭합니다.

7.  다음 **홉 선택 페이지의** 목록에서 비즈니스용 Skype 서버 프런트 엔드 풀을 선택합니다.

8.  **마침** 을 클릭합니다.

9.  최상위 노드 비즈니스용 **Skype 서버를** 선택한 다음  작업 메뉴에서 토폴로지 **게시를 클릭합니다.**
    
    신뢰할 **수 있는 응용 프로그램** 풀을 성공적으로 만들어 올바른 프런트 엔드 풀과 연결해야 합니다.


## <a name="view-a-list-of-trusted-applications"></a>신뢰할 수 있는 응용 프로그램 목록 보기

비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버 환경에 배포한 신뢰할 수 있는 응용 프로그램 목록을 볼 수 있습니다. 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 신뢰하는 Microsoft UCMA(Unified Communications Managed API) 3.0 Core SDK를 기반으로 하는 응용 프로그램입니다. 이 트러스트 관계는 다음 목록에 요약됩니다.

  - 신뢰할 수 있는 응용 프로그램은 비즈니스용 Skype 서버에서 인증할 수 없습니다.

  - 신뢰할 수 있는 응용 프로그램은 SIP 트랜잭션, 연결 또는 VoIP(Voice over Internet Protocol) 통화에 대해 비즈니스용 Skype 서버에서 스로틀되지 않습니다.

  - 신뢰할 수 있는 응용 프로그램은 모든 사용자를 가장할 수 있으며, 로스터에 나타나지 않고도 회의에 참가할 수 있습니다.

  - 신뢰할 수 있는 응용 프로그램은 고가용성 및 탄력적입니다.

비즈니스용 Skype 서버 제어판에서 응용 프로그램의 이름, 응용 프로그램이 실행되는 풀 및 사용하는 포트를 볼 수 있습니다.


### <a name="to-view-a-list-of-trusted-applications"></a>신뢰할 수 있는 응용 프로그램 목록을 표시

1.  CsServerAdministrator, CsAdministrator, CsHelpDesk 또는 CsViewOnlyAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다. 비즈니스용 Skype 서버에서 사용할 수 있는 미리 정의한 관리 역할에 대한 자세한 내용은 [RBAC(역할 기반 액세스 제어)를 참조하세요.](../plan-your-deployment/security/role-based-access-control-rbac.md)

2.  브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.

3.  왼쪽 탐색 모음에서 **토폴로지** 및 신뢰할 수 있는 응용 **프로그램 클릭**

4.  신뢰할 수 **있는 응용 프로그램** 페이지에서 열 제목을 클릭하여 필요한 경우 응용 프로그램을 정렬합니다.


## <a name="view-trusted-application-information"></a>신뢰할 수 있는 응용 프로그램 정보 보기

신뢰할 수 있는 응용 프로그램에 대한 정보는 Windows PowerShell **Get-CsTrustedApplication** cmdlet을 사용하여 볼 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell. 


### <a name="to-view-trusted-applications"></a>신뢰할 수 있는 응용 프로그램을 보려면

신뢰할 수 있는 모든 응용 프로그램을 보시다시피 비즈니스용 Skype 서버 관리 셸에 다음 명령을 입력하고 Enter를 누르고 있습니다.
    
        Get-CsConferenceDisclaimer
    
   이 명령은 신뢰할 수 있는 각 응용 프로그램에 대해 다음과 비슷한 정보를 반환합니다.
    
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
    
   자세한 내용은 [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)을 참조하십시오.
