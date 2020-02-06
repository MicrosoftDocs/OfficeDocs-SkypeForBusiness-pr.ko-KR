---
title: 익명 사용자 지원을 위한 회의 정책 할당
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 익명 사용자를 지원 하도록 회의 정책을 구성 하 고 특정 사용자에 게 해당 회의 정책을 적용 하 여 익명 사용자를 초대할 수 있는 사용자를 제어 합니다.
ms.openlocfilehash: b5427ec96d3593cf87656f562acf0afc183b92d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818419"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 익명 사용자를 지원 하도록 회의 정책 할당 


기본적으로 모든 사용자는 익명 사용자를 초대 하 여 모임에 참가할 수 없습니다. 익명 사용자를 지원 하도록 회의 정책을 구성 하 고 특정 사용자에 게 해당 회의 정책을 적용 하 여 익명 사용자를 초대할 수 있는 사용자를 제어 합니다. 익명 사용자를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 정책 만들기](../../conferencing/create-policies.md) 및 비즈니스용 skype server에 대 한 [페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요.

이 섹션의 절차를 사용 하 여 이미 만든 회의 정책을 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.

> [!NOTE]  
> 사용자가 익명 사용자를 초대할 수 있도록 하는 정책을 구성 하 고 적용 하는 것 외에도 조직의 익명 사용자에 대 한 지원을 사용 하도록 설정 해야 합니다. 자세한 내용은 [비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어 하는 정책 구성을](../external-access-policies/configure-policies-to-control-public-user-access.md)참조 하세요.


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>모임에서 익명 참가에 대 한 사용자 정책을 구성 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다. 

3.  왼쪽 탐색 모음에서 **회의**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
    1.  새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다. 사용자 정책이 어떤 역할을 하는지 나타내는 **이름** 필드에 고유한 이름을 만듭니다 (예: 익명 사용자와의 통신을 가능 하 게 하는 사용자 정책에 **익명** 허용).
    
    2.  기존 사용자 정책을 구성 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

4.  **회의 정책** 대화 상자에서 **참가자가 익명 사용자 초대를 허용** 확인란을 선택 합니다.

5.  **커밋**을 클릭합니다.

6.  왼쪽 탐색 모음에서 **사용자**를 클릭 하 고 구성 하려는 사용자 계정에서 검색 합니다.

7.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

8.  **회의 정책**에서 **비즈니스용 Skype 서버 사용자 편집** 에서이 사용자에 게 적용 하려는 익명 사용자 액세스 구성이 있는 사용자 정책을 선택 합니다.  

    > [!NOTE]  
    > 자동 설정은 기본 서버 설치 설정을 적용 하 고 서버에 의해 자동으로 적용 됩니다. <STRONG> &lt;&gt; </STRONG>


사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면 조직의 익명 사용자에 대 한 지원도 사용 하도록 설정 해야 합니다. 자세한 내용은 [비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어 하는 정책 구성을](../external-access-policies/configure-policies-to-control-public-user-access.md)참조 하세요.

