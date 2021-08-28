---
title: 사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: '사용자가 다른 조직의 비즈니스용 Skype 대화를 할 수 있도록 또는 외부 연락처가 대화할 수 있도록 구성하는 방법을 참조합니다. '
ms.openlocfilehash: 987fc8120a06e1a96df4d33cf3f42ba90bc123ed
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602023"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>사용자가 외부 비즈니스용 Skype 사용자와 연락하도록 허용

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
다음을 수행하면 이 문서의 단계를 수행합니다.
  
- 비즈니스에 다른 도메인에 사용자가 있습니다. 예를 들어 Rob@ContosoEast.com Ann@ContosoWest.com.

- 조직의 사람들이 조직 외부의 특정 비즈니스용 Skype 사용자와 연락할 수 있도록 할 수 있습니다.

- 전자 메일 주소를 사용하여 비즈니스용 Skype 다른 사람이 사용자와 연락할 수 있도록 합니다. 사용자와 사용자가 기본 설정 비즈니스용 Skype 경우 자동으로 작동됩니다. 그렇지 않은 경우 해당 구성이 도메인을 차단하지 않는지 확인해야 합니다.

## <a name="enable-business-to-business-communications-for-your-users"></a>사용자에 대한 비즈니스 간 통신 사용

<a name="bk_preview"> </a>

이 [통신을](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Microsoft 365 Office 365 관리 권한이 있어야 합니다.

![관리 센터를 사용하여 Microsoft Teams 로고를 Teams ](../images/teams-logo-30x30.png) **아이콘**
  
1. 관리자 계정 또는 Microsoft 365 Office 365 로그인합니다.

2. 관리 센터에서 관리 센터  >  Teams.

    ![관리자를 Teams 선택하세요.](../images/MS-Teams-Admin.png)
  
3. Teams 레거시 포털에서 Skype  >  
  ![ SfB 레거시 포털 선택을 선택합니다.](../images/SFBlegacy-size65.png)

4. **비즈니스용 Skype 관리 센터** 에서 **조직** > **외부 통신** 을 선택합니다.
5. 드롭다운 상자에서 특정 비즈니스 또는 다른 도메인의 사용자와의 통신을 설정하려면 **허용된 도메인에 대해서만** 을 선택합니다.

    또는 정책이 열려 있는 다른 모든 사용자와의 통신을 사용하도록 설정하려는 비즈니스용 Skype 차단된 도메인을 제외하고 **On을 선택해야 합니다.** 기본 설정입니다.

6. **차단되거나** 허용되는 도메인에서 허용할 도메인 이름을 선택하고 **+** 추가합니다.

7. 다른 조직의 관리자가 해당 관리자 센터에서 비즈니스용 Skype **합니다.** 예를 들어 **허용되는** 도메인 목록에서 관리자는 비즈니스용 도메인을 입력해야 합니다.

8. 방화벽을 Windows 경우 비즈니스용 Skype 포트가 자동으로 열립니다.

    조직에서 다른 방화벽 솔루션을 사용하여 네트워크의 컴퓨터를 인터넷에 연결하지 못하도록 제한하는 경우 클라이언트 컴퓨터가 다음 URL 및 [IP 주소 범위에](/microsoftteams/office-365-urls-ip-address-ranges)Office 365 수 있도록 합니다. 이 경우 방화벽 또는 프록시 인프라 구성의 아웃바운드 허용 목록에 FQDNs를 추가해야 할 수 있습니다. **\* .api.skype.com** \* *_, .users.storage.live.com_* 및 graph.skype.com.  방화벽에서 이러한 포트를 여는 방법에 대한 지침은 함께 제공된 설명서를 참조하세요.

    열 필요가 있는 모든 포트 목록은 URL 및 [IP Office 365 을 참조하세요.](/microsoftteams/office-365-urls-ip-address-ranges)

9. 조직의 관리자가 다음 단계를 수행한지 확인하세요.

10. **테스트할 때까지 최대 24시간을 기다릴 수 있습니다.** 외부 통신 설정을 변경하면 변경 내용이 모든 데이터 센터에 채워지는 데 최대 24시간이 걸릴 수 있습니다.

![](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)Skype 사용자가 무료 소비자 앱인 무료 소비자 앱을 사용하는 Skype IM을 검색하도록 허용할 수 있습니다. 자세한 내용은 사용자가 연락처를 비즈니스용 Skype [을 Skype 참조합니다.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>테스트 및 문제 해결

<a name="bk_preview"> </a>

 **비즈니스 간 통신을 설정할 때 발생하는 가장 일반적인 문제는 URL 및 [IP](/microsoftteams/office-365-urls-ip-address-ranges) 주소 범위를 Office 365 것입니다.**
  
설정을 테스트하려면 회사 방화벽에 비즈니스용 Skype 사용자에 대한 연락처가 필요합니다.
  
1. 외부 통신 설정을 변경한 후 최대 **24시간 대기하여 테스트합니다.**

2. 비즈니스용 Skype 대화에서 연락처를 검색하고 채팅에 비즈니스용 Skype 요청을 전송합니다.

    회사 정책으로 인해 보낼 수 없는 메시지가 표시될 경우 URL 및 IP 주소 범위에 대한 Office 365 다시 확인해야 [합니다.](/microsoftteams/office-365-urls-ip-address-ranges)

3. 채팅 요청을 비즈니스용 Skype 연락처에 문의하세요. 요청을 받지 못한 경우 (방화벽 설정이 올바른지 이미 확인했다고 가정한다면) 방화벽 설정에 문제가 있는 것입니다.

4. 방화벽이 문제인지 여부를 테스트하는 또 다른 방법은 커피숍과 같은 방화벽 뒤에 있지 않은 Wifi 위치로 이동하는 것입니다. 대화 비즈니스용 Skype 대화에 대한 요청을 보낼 수 있습니다. 메시지가 이 작업을 거치지만 작업 중이 아닌 경우 방화벽이 문제인 것을 알 수 있습니다.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>다른 비즈니스와 연결할 때 다른 사람을 찾고 찾을 수 있는 방법

<a name="bk_preview"> </a>

다른 사용자와 외부 통신을 사용하도록 비즈니스용 Skype 사용자들은 로그인 이름을 검색하여 비즈니스용 Skype 페더링된 사용자를 찾을 수 있습니다. 예제는 Rob@contoso.com. 그런 다음 연락처 목록에 해당 사람을 추가해야 합니다.
  
![페더리드 비즈니스에서 사용자를 찾으하려면 해당 전자 메일 주소를 검색해야 합니다(일반적으로 로그인 이름도 해당).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>팁 기업과의 통신 설정에 대한 정보

<a name="bk_preview"> </a>

- 2015년 비즈니스용 Skype 및 비즈니스용 Skype 페더년에 대한 페더리를 구성하기 위해 이 문서를 참조하세요. 비즈니스용 Skype 온라인 을 [참조하세요.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)

- Lync와 비즈니스용 Skype 페더링을 구성하기 위해 이 문서를 [참조하세요. Lync Online](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)고객에 대한 페더링 지원 구성 을 참조하세요.

- 두 비즈니스용 Skype 또는 Microsoft 365 Office 365 서로 통신하는 경우 두 조직에서 설정된 비즈니스용 Skype 기능(예: 비디오 대화 또는 데스크톱 공유)만 사용할 수 있습니다.

- 조직의 비즈니스용 Skype 사용자가 In-Place 소송 보류에 놓이면 해당 사용자와 다른 사용자 비즈니스용 Skype 또는 Skype 대화가 사서함의 복구 가능한 항목에 저장됩니다.  이러한 대화는 사서함의 **대화** 기록 폴더에 저장되지 않습니다.

## <a name="turn-off-external-communication-for-specific-individuals"></a>특정 개인에 대한 외부 통신 해제

<a name="bk_preview"> </a>

전체 비즈니스에 대한 외부 통신을 사용하도록 설정한 후 특정 개인에 대해 해당 통신을 해제할 수 있습니다.
  
1. 관리자 계정 또는 Microsoft 365 Office 365 로그인합니다.

2. 관리 센터에서 **사용자** 활성  >  **사용자로 이동합니다.**

3. 사용자 목록에서 사용자를 선택한 다음 추가 정보에서 설정 속성  **편집을 비즈니스용 Skype 클릭합니다.**

    ![선택 비즈니스용 Skype](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. 관리 **비즈니스용 Skype** 에서 **외부 통신을 선택하세요.**

    옵션 **페이지에서** 모든 선택이 선택됩니다. 사용하지 않도록 설정하려는 통신을 선택 취소합니다. 다음 이미지는 Jakob이 다른 신뢰할 수 있는 비즈니스 사용자와 통신할 수 있지만 다른 사용자와는 통신할 Skype 보여줍니다.

    ![외부 연락처 선택](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. 저장을 **선택 합니다.**

> [!NOTE]
> 변경 내용이 적용될 때까지 최대 24시간 동안 기다려야 할 수 있습니다.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>관련 주제

<a name="bk_preview"> </a>

[비즈니스용 Skype 온라인 설정](set-up-skype-for-business-online.md)
  
[비즈니스용 Skype 사용자가 Skype 연락처를 추가하도록 허용](let-skype-for-business-users-add-skype-contacts.md)
