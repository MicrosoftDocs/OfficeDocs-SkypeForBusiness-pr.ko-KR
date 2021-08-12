---
title: 페더레이션 파트너로 보관 고지 사항 보내기를 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 83c548f948c4c368ba1d8186fbdc9f212b9fb67b463f8eaec845f7698f4c0720
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313176"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>2016년 10월 2일부로 보관 고지 조항 보내기 사용 또는 사용 안 비즈니스용 Skype 서버

에지 서버를 배포하고 조직에 대해 페더레이션을 사용하도록 설정할 때 보관 고지 사항을 페더레이션 파트너에게 자동으로 보낼지 여부를 지정해야 합니다. 외부 통신을 보관할 경우에는 보관 고지 사항을 보낼 수 있도록 설정해야 합니다 해당 구성을 변경하려면 이 항목의 절차를 사용합니다.

> [!NOTE]
> 다음 절차에서는 이미 조직에 대해 페더레이션이 사용하도록 설정되어 있다고 가정합니다. 페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 안 [하도록 설정을 참조합니다.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **액세스 에지 구성** 을 클릭합니다.

4.  **액세스 에지 구성** 탭에서 **전역**, **편집**, **자세한 정보 표시** 를 차례로 클릭합니다.

5.  **액세스 에지 구성 편집** 의 **페더레이션 사용자와의 통신 사용** 에서 **페더레이션 파트너에게 보관 고지 사항 보내기** 확인란을 선택하거나 선택 취소하여 보관 고지 사항을 자동으로 보내거나 보내지 않도록 설정할 수 있습니다.

6.  **커밋** 을 클릭합니다.

페더니트 사용자가 비즈니스용 Skype 서버 사용자와 공동 작업을 할 수 있도록 페더된 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다. 특정 페더링 도메인에 대한 액세스를 제어하는 데 대한 자세한 내용은 [Configure support for allowed external domains을 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 보관 고지 Windows PowerShell 사용 안 하게 설정

보관 고지 조항의 사용은 Windows PowerShell cmdlet을 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다. 이 cmdlet은 관리 셸 또는 비즈니스용 Skype 서버 원격 세션에서 실행할 수 Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>보관 고지 조항을 사용하도록 설정하려면

  - 보관 고지 사항을 사용하도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 True($True)로 설정합니다.
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>보관 고지 조항을 사용하지 않도록 설정

  - 보관 고지 사항을 사용하지 않도록 설정하려면 **EnableArchivingDisclaimer** 속성 값을 False($False)로 설정합니다.
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


