---
title: 페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 지원하는 공용 IM(인스턴트 메시징) 공급자의 사용자 및 파트너 도메인을 포함하여 신뢰할 수 있는 고객 또는 파트너 조직에 계정이 있는 사용자가 조직 내 사용자와 공동 작업할 수 있도록 하려면 페더레이션 지원이 필요합니다.
ms.openlocfilehash: 638a5d0274679a9d9745656e1b2d740791185b04
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854352"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a>2016년 8월 1일부로 설정하거나 사용하지 않도록 비즈니스용 Skype 서버

지원하는 공용 IM(인스턴트 메시징) 공급자의 사용자 및 파트너 도메인을 포함하여 신뢰할 수 있는 고객 또는 파트너 조직에 계정이 있는 사용자가 조직 내 사용자와 공동 작업할 수 있도록 하려면 페더레이션 지원이 필요합니다. 또한 호스팅되는 Exchange 서비스 공급자를 사용하여 Microsoft Exchange Online 등의 호스팅되는 Exchange 서비스에 사서함이 있는 Enterprise Voice 사용자에게 음성 메일을 제공하려는 경우에도 페더레이션이 필요합니다. 이러한 외부 도메인과 트러스트 관계를 설정한 경우 해당 도메인의 사용자에게 배포에 액세스하고 보안 통신에 참여할 수 비즈니스용 Skype 서버 있습니다. 이러한 신뢰 관계는 페더레이션이라고 하며, Active Directory 신뢰 관계와는 관련이 없고 해당 관계에 종속되지도 않습니다.

페더레이션 도메인 사용자의 액세스를 지원하려면 페더레이션을 사용하도록 설정해야 합니다. 조직의 페더레이션을 사용하도록 설정하는 경우 다음 옵션을 구현할지 여부도 지정해야 합니다.

  - **파트너 도메인 검색 사용**   이 옵션을 사용하도록 설정하면 비즈니스용 Skype 서버 DNS(Domain Name System) 레코드를 사용하여 허용 도메인 목록에 없는 도메인을 검색하여 검색된 페더링 파트너로부터 들어오는 트래픽을 자동으로 평가하고 트러스트 수준, 트래픽 양 및 관리자 설정에 따라 해당 트래픽을 제한하거나 차단합니다. 이 옵션을 선택하지 않은 경우 허용 도메인 목록에 포함되는 도메인의 사용자에 한해 페더전 사용자 액세스가 사용하도록 설정됩니다. 이 옵션을 선택하는지 여부에 따라 페더링 도메인에서 액세스 에지 서비스를 실행하는 특정 서버에 대한 액세스 제한을 포함하여 개별 도메인을 차단하거나 허용하도록 지정할 수 있습니다. 페더링 도메인의 액세스를 제어하는 데 대한 자세한 내용은 [Configure support for allowed external domains을 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)

  - **페더레이션 파트너에게 보관 고지 사항 전송**    해당 배포에서 보관 기능이 배치되었음을 알리는 보관 고지 사항이 페더레이션 파트너에게 전송됩니다. 페더레이션 파트너 도메인과의 외부 통신에 대한 보관을 지원하는 경우, 파트너에게 메시지가 보관된다는 경고를 보내기 위해 보관 고지 사항 알림을 사용하도록 설정해야 합니다.

나중에 페더레이션 도메인 사용자의 액세스를 일시적으로 또는 영구적으로 차단하려면 조직의 페더레이션을 사용하지 않도록 설정하면 됩니다. 이 섹션의 절차를 사용하여 조직에 지원할 적절한 페더레이션 옵션 지정을 비롯하여 조직의 페더레이션 사용자 액세스를 사용하거나 사용하지 않도록 설정하십시오.

> [!NOTE]  
> 조직에 대해 페더레이션을 사용하도록 설정하면 액세스 에지 서비스를 실행하는 서버가 페더레이션 도메인으로 라우팅하는 작업만 지원하도록 지정됩니다. 페더레이션 사용자 액세스를 지원하는 정책도 하나 이상 구성해야 페더레이션 도메인의 사용자가 조직의 IM 또는 회의에 참가할 수 있습니다. 또한 공용 IM 연결을 지원하는 정책도 하나 이상 구성해야 공용 IM 서비스 공급자의 사용자가 조직의 IM 또는 회의에 참가할 수 있습니다. 비즈니스용 Skype 서버 라우팅 정보를 제공하는 호스팅된 음성 메일 정책을 구성할 때까지는 호스팅된 Exchange 서비스를 사용하여 사서함이 호스팅된 Exchange 서비스에 있는 사용자에 대해 전화 응답, Outlook Voice Access(음성 메일 포함) 또는 자동 전화 응답 서비스를 제공할 수 없습니다. 다른 조직의 페더링 도메인 사용자와 통신하는 정책을 구성하는 데 대한 자세한 내용은 [조직에 대한 SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md)페더전 도메인 관리를 참조합니다. 또한 IM 서비스 공급자 사용자와의 통신을 지원하려는 경우 이를 지원하는 정책을 구성하고 지원할 개별 서비스 공급자에 대한 지원도 구성해야 합니다. 자세한 내용은 [Manage SIP federated providers for your organization를 참조합니다.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>조직의 페더레이션 사용자 액세스를 사용하거나 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **액세스 에지 구성** 을 클릭합니다.

4.  **액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.

5.  **액세스 에지 구성 편집** 에서 다음 중 하나를 수행합니다.
    
      - 조직의 페더레이션 사용자 액세스를 사용하도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란을 선택합니다.
    
      - 조직의 페더레이션 사용자 액세스를 사용하지 않도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란의 선택을 취소합니다.

6.  **페더레이션 사용자와의 통신 사용** 확인란을 선택한 경우 다음을 수행하십시오.
    
    1.  파트너 도메인 자동 검색을 지원하려면 **파트너 도메인 검색 사용** 확인란을 선택합니다.
    
    2.  조직에서 외부 통신 보관을 지원하는 경우 **페더레이션 파트너에게 보관 고지 사항 보내기** 확인란을 선택합니다.

7.  **커밋** 을 클릭합니다.

페더러가 비즈니스용 Skype 서버 사용자와 공동 작업을 할 수 있도록 페더러가 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책을 구성해야 합니다. 자세한 내용은 [Configure policies to control federated user access을 참조합니다.](../external-access-policies/configure-policies-to-control-federated-user-access.md) 특정 페더니트 도메인에 대한 액세스를 제어하려면 허용된 외부 도메인에 대한 지원 [구성을 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 페더링 및 공용 IM 연결 Windows PowerShell 사용 안 하게 설정

페더ation 및 공용 IM 연결은 Windows PowerShell cmdlet을 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 

## <a name="to-enable-federation-and-public-im-connectivity"></a>페더임 및 공용 IM 연결을 사용하도록 설정하려면

  - 페더레이션 및 공용 IM 연결을 사용하도록 설정하려면 **AllowFederatedUsers** 속성 값을 True($True)로 설정합니다.<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a>페더임 및 공용 IM 연결을 사용하지 않도록 설정

  - 페더레이션 및 공용 IM 연결을 사용하지 않도록 설정하려면 **AllowFederatedUsers** 속성 값을 False($False)로 설정합니다.<br/><br/>Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

