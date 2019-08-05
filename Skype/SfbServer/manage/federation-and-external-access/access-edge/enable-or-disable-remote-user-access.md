---
title: 원격 사용자 액세스 사용 또는 사용 안 함
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 원격 사용자에 대 한 원격 사용자 액세스를 사용 하도록 설정 하면 지원 되는 원격 사용자가 인터넷을 통해 연결 되며 비즈니스용 Skype 서버를 사용 하 여 내부 사용자와 공동 작업 하기 위해 VPN을 사용 하 여 연결할 필요가 없습니다.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188868"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 원격 사용자 액세스 사용 또는 사용 안 함

원격 사용자는 조직 내에서 영구 Active Directory id를 보유 하 고 있는 조직의 사용자입니다. 원격 사용자는 조직의 네트워크에 연결 되어 있지 않은 경우 VPN (가상 사설망)을 사용 하 여 네트워크 외부에서 비즈니스용 Skype 서버에 로그인 하는 경우가 많습니다. 원격 사용자에 게 가정에서 근무 하는 직원이 나 이동 중에도 엔터프라이즈 자격 증명을 부여 받은 신뢰할 수 있는 공급 업체와 같은 기타 원격 작업자를 포함 합니다. 원격 사용자에 대 한 원격 사용자 액세스를 사용 하도록 설정 하면 지원 되는 원격 사용자가 인터넷을 통해 연결 되며 비즈니스용 Skype 서버를 사용 하 여 내부 사용자와 공동 작업 하기 위해 VPN을 사용 하 여 연결할 필요가 없습니다.

원격 사용자 액세스를 지원 하려면 원격 사용자 액세스를 사용 하도록 설정 해야 합니다. 원격 사용자 액세스를 사용 하도록 설정 하면 전체 조직에 대해 사용 하도록 설정 됩니다. 나중에 일시적으로 또는 영구적으로 원격 사용자 액세스를 방지 하려면 조직에 맞게 사용 하지 않도록 설정할 수 있습니다. 이 섹션의 절차를 사용 하 여 조직에 대 한 원격 사용자 액세스를 설정 하거나 해제 합니다.


> [!NOTE]  
> 원격 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버에서 원격 사용자와의 통신을 지원 하지만 원격 사용자가 조직에서 인스턴트 메시징 (IM) 이나 회의에 참가할 수 없는 경우에만 구성 됩니다. 원격 사용자 액세스 사용을 관리 하는 하나 이상의 정책. 한 정책 수준에서 적용 되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용 된 설정을 무시할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향). 즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다. 원격 사용자 액세스 사용에 대 한 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 원격 사용자 액세스 제어 정책 구성을](../external-access-policies/configure-policies-to-control-remote-user-access.md)참조 하세요.


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>조직의 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.

4.  **액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **액세스에 지 구성 편집**에서 다음 중 하나를 수행 합니다.
    
      - 조직의 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자 액세스 사용** 확인란을 선택 합니다.
    
      - 조직의 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자 액세스 사용** 확인란의 선택을 취소 합니다.

6.  **커밋**을 클릭합니다.

원격 사용자가 비즈니스용 Skype Server를 실행 하는 서버에 로그인 할 수 있도록 하려면 하나 이상의 외부 액세스 정책을 구성 하 여 원격 사용자 액세스를 지원 해야 합니다. 자세한 내용은 [비즈니스용 Skype 서버에서 원격 사용자 액세스를 제어 하도록 정책 구성을](../external-access-policies/configure-policies-to-control-remote-user-access.md)참조 하세요.


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Windows PowerShell cmdlet을 사용 하 여 원격 사용자 액세스 사용 또는 사용 안 함

Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 원격 사용자 액세스를 관리할 수 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 

## <a name="to-enable-remote-user-access"></a>원격 사용자 액세스를 사용 하도록 설정 하려면

  - 원격 사용자 액세스를 사용 하도록 설정 하려면 **Allowout 사용자** 속성 값을 True ($True)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>원격 사용자 액세스를 사용 하지 않도록 설정 하려면

  - 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **Allowout함 사용자** 속성 값을 False ($False)로 설정 합니다.
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


