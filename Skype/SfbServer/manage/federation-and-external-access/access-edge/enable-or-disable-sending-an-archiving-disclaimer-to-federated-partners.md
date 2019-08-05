---
title: 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188862"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 페더레이션 파트너에 게 보관 고 지 사항 전송 사용 또는 사용 안 함

Edge 서버를 배포 하 고 조직에 대해 페더레이션을 사용 하도록 설정한 경우에는 페더레이션 파트너에 게 자동으로 보관 거부를 보낼지 여부를 지정 해야 합니다. 외부 통신을 보관 하는 경우 보관 고 지 사항을 보낼 수 있습니다. 이 항목의 절차를 사용 하 여 해당 구성을 변경할 수 있습니다.

> [!NOTE]
> 다음 절차에서는 조직에 페더레이션이 이미 설정 되어 있다고 가정 합니다. 페더레이션 사용에 대 한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](enable-or-disable-remote-user-access.md)참조 하세요.


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>페더레이션 파트너에 게 보관 고 지 사항 보내기를 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **Edge 구성 액세스**를 클릭 합니다.

4.  **액세스 경계 구성** 탭에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **액세스에 지 구성 편집**의 **페더레이션 사용자와 통신 사용**에서 페더레이션 **파트너에 게 보관 거부 보내기** 확인란을 선택 하거나 선택을 취소 하 여 자동으로 보관을 설정 하거나 해제 합니다. 고 지 사항.

6.  **커밋**을 클릭합니다.

페더레이션 사용자가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업을 할 수 있도록 하려면 하나 이상의 외부 액세스 정책이 페더레이션 사용자 액세스를 지원 하도록 구성 되어 있어야 합니다. 특정 페더레이션 도메인에 대 한 액세스 제어에 대 한 자세한 내용은 [허용 된 외부 도메인에 대 한 지원 구성을](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)참조 하세요.


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 보관 고 지 사항 사용 또는 사용 안 함

보관 고 지 사항 사용은 Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

## <a name="to-enable-the-archiving-disclaimer"></a>보관 고 지 사항을 설정 하려면

  - 보관 부인를 사용 하도록 설정 하려면 **EnableArchivingDisclaimer** 속성 값을 True ($True)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>보관 고 지 사항을 사용 하지 않도록 설정 하려면

  - 보관 고 지 사항을 사용 하지 않으려면 **EnableArchivingDisclaimer** 속성 값을 False ($False)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


