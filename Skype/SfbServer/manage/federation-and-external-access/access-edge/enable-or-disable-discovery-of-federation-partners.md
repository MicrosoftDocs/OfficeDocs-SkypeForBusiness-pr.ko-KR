---
title: 페더레이션 파트너 검색을 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: 에지 서버를 배포하고 조직에 대해 페더레이션을 사용하도록 설정하는 시점에 페더레이션 파트너 도메인의 자동 검색 지원 여부를 지정해야 합니다.
ms.openlocfilehash: 4e425566fb0b8aa463c93f0940582487dabaae3d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830012"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>2016년 8월 1일부로 비즈니스용 Skype 서버

에지 서버를 배포하고 조직에 대해 페더레이션을 사용하도록 설정하는 시점에 페더레이션 파트너 도메인의 자동 검색 지원 여부를 지정해야 합니다. 해당 구성을 변경하려면 이 항목의 절차를 사용합니다.

> [!NOTE]  
> 다음 절차에서는 이미 조직에 대해 페더레이션이 사용하도록 설정되어 있다고 가정합니다. 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 안 [하도록 설정을 참조합니다.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>조직에 대해 페더레이션 도메인의 자동 검색을 사용하거나 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다.

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **액세스 에지 구성** 을 클릭합니다.

4.  **액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.

5.  **페더레이션 사용자와의 통신 사용** 아래의 **액세스 에지 구성 편집** 에서 **파트너 도메인 검색 사용** 확인란을 선택 또는 선택 취소하여 파트너 도메인의 자동 검색을 사용하거나 사용하지 않도록 설정합니다.

6.  **커밋** 을 클릭합니다.

페더니트 사용자가 비즈니스용 Skype 서버 사용자와 공동 작업을 할 수 있도록 페더된 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다. 자세한 내용은 [Enable or disable federation and public IM connectivity을 참조합니다.](enable-or-disable-federation-and-public-im-connectivity.md) 특정 페더링 도메인에 대한 액세스를 제어하는 데 대한 자세한 내용은 SIP 페더링 도메인 관리 및 [SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) 페더링 공급자 관리를 [참조합니다.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 페더링 파트너 검색을 활성화 또는 Windows PowerShell 수 있습니다.

페더ation 파트너 검색은 Windows PowerShell cmdlet을 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>페더미스 파트너 검색을 사용하도록 설정하려면

  - 페더레이션 파트너 검색을 사용하도록 설정하려면 **EnablePartnerDiscovery** 속성의 값을 True($True)로 설정합니다. 이 속성 값을 변경하려면 DNS SRV 라우팅을 사용하도록 설정해야 합니다.<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>페더미스 파트너 검색을 사용하지 않도록 설정

  - 페더레이션 파트너 검색을 사용하지 않도록 설정하려면 **EnablePartnerDiscovery** 속성의 값을 False($False)로 설정합니다.<br/><br/>Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

