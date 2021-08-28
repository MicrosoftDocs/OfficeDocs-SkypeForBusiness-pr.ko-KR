---
title: 원격 사용자 액세스를 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 원격 사용자에 대한 원격 사용자 액세스를 사용하도록 설정하는 경우 지원되는 원격 사용자는 인터넷을 통해 연결하며, VPN을 사용하여 연결할 필요는 비즈니스용 Skype 서버 없습니다.
ms.openlocfilehash: c20f6891b463f44fdcd424ca870fbba0826d33bd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608195"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>2016에서 원격 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 비즈니스용 Skype 서버

원격 사용자는 조직 내에서 영구 Active Directory ID를 가지는 조직의 사용자입니다. 원격 사용자는 조직의 비즈니스용 Skype 서버 연결되지 않은 경우 VPN(가상 사설망)을 사용하여 네트워크 외부에서 로그인합니다. 원격 사용자에는 회사 자격 증명이 부여된 신뢰할 수 있는 공급업체와 같은 집이나 도로에서 근무하는 직원과 기타 원격 작업자가 포함됩니다. 원격 사용자에 대한 원격 사용자 액세스를 사용하도록 설정하는 경우 지원되는 원격 사용자는 인터넷을 통해 연결하며, VPN을 사용하여 연결할 필요는 비즈니스용 Skype 서버 없습니다.

원격 사용자 액세스를 지원하려면 원격 사용자 액세스를 사용하도록 설정해야 합니다. 원격 사용자 액세스를 사용하도록 설정하면 전체 조직에 대해 원격 사용자 액세스를 사용하도록 설정할 수 있습니다. 나중에 원격 사용자 액세스를 일시적으로 또는 영구적으로 차단하려는 경우 조직에서 사용하지 않도록 설정할 수 있습니다. 이 섹션의 절차에 따라 조직에 대한 원격 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.


> [!NOTE]  
> 원격 사용자 액세스를 사용하도록 설정하는 것은 액세스 에지 서비스를 실행하는 서버가 원격 사용자와의 통신을 지원하도록 지정하지만 원격 사용자는 원격 사용자 액세스 사용을 관리하기 위한 정책도 하나 이상 구성해야만 조직의 IM(인스턴트 메시징) 또는 회의에 참가할 수 있습니다. 비즈니스용 Skype 서버 수준에서 적용되는 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다. 비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다. 즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다. 원격 사용자 액세스 사용에 대한 정책을 구성하는 자세한 내용은 [Configure policies to control remote user access in 비즈니스용 Skype 서버.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>조직에 대한 원격 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.

2.  브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버 열 수 있습니다. 

3.  왼쪽 탐색 모음에서 연결 및 외부 액세스를 클릭한 다음 액세스 에지 구성 **을 클릭합니다.**

4.  **액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.

5.  **액세스 에지 구성 편집** 에서 다음 중 하나를 수행합니다.
    
      - 조직에서 원격 사용자 액세스를 사용하도록 설정하려면 원격 사용자 액세스 사용 **확인란을** 선택합니다.
    
      - 조직에 대한 원격 사용자 액세스를 사용하지 않도록 설정하려면 원격 사용자 액세스 사용 **확인란의 선택을** 취소합니다.

6.  **커밋** 을 클릭합니다.

원격 사용자가 원격 사용자를 실행 중인 서버에 비즈니스용 Skype 서버 원격 사용자 액세스를 지원하도록 외부 액세스 정책을 하나 이상 구성해야 합니다. 자세한 내용은 [Configure policies to control remote user access in 비즈니스용 Skype 서버.](../external-access-policies/configure-policies-to-control-remote-user-access.md)


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>cmdlet을 사용하여 원격 사용자 액세스를 Windows PowerShell 사용 안 하도록 설정

원격 사용자 액세스는 cmdlet 및 Windows PowerShell 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다. 이 cmdlet은 비즈니스용 Skype 서버 2013 관리 셸 또는 2013 관리 셸의 원격 세션에서 실행할 Windows PowerShell. 

## <a name="to-enable-remote-user-access"></a>원격 사용자 액세스를 사용하도록 설정하려면

  - 원격 사용자 액세스를 사용하도록 설정하려면 **AllowOutsideUsers** 속성 값을 True($True).
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>원격 사용자 액세스를 사용하지 않도록 설정

  - 원격 사용자 액세스를 사용하지 않도록 설정하기 위해 **AllowOutsideUsers** 속성의 값을 False($False).
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


