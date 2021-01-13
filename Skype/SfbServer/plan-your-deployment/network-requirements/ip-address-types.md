---
title: 비즈니스용 Skype에서 IP 주소 유형 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: '요약: 비즈니스용 Skype 서버를 구현하기 전에 아래 IP 주소 유형 고려 사항을 검토합니다.'
ms.openlocfilehash: d5e50b8d3a964bb4e4dcbc502527e5249af3a1e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825264"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>비즈니스용 Skype에서 IP 주소 유형 구성

**요약:** 비즈니스용 Skype 서버를 구현하기 전에 아래 IP 주소 유형 고려 사항을 검토합니다.

토폴로지 작성기에서 구성한 토폴로지 설정을 사용하여 IP 주소 유형을 배포합니다. 이 섹션에서는 프런트 엔드 서버, 중재 서버 및 에지 서버에 IP 주소 유형을 배포하는 방법을 설명합니다.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>프런트 엔드 서버에 IP 주소 유형 배포

토폴로지 작성기에서 다음 절차의 단계를 수행하여 프런트 엔드 서버에 IP 주소 유형을 배포합니다.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>프런트 엔드 서버에 IP 주소 유형을 배포하려면

1. **Enterprise Edition 프런트 엔드 풀** 아래에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 후 **속성 편집** 을 선택합니다. 또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.

2. **속성 편집** 대화 상자에서 구성할 IP 주소 유형을 선택합니다. 이중 스택 구성의 경우 **IPv4** 사용 및 **IPv6 사용을 선택합니다.**

   **프런트 엔드 서버 풀에 대한 속성 편집 대화 상자**

   - **구성된 모든 IP 주소**. 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있도록 하려면 이 옵션을 선택합니다.

     > [!NOTE]
     > 이것이 IP 버전 6(IPv6) 구성에서 권장되는 옵션입니다.

   - **선택한 IP 주소로 서비스 사용 제한**. 새 서버에서 사용할 특정 주소를 지정하려면 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 **기본 IP 주소** 의 값을 입력해야 합니다.

   - **기본 IP 주소**. 서버에서 PSTN(공중 전화망)을 제외한 모든 통신에 사용할 IP 주소를 입력합니다. 입력하는 IP 주소는 선택한 주소 유형의 형식과 일치해야 합니다.

   - **PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에 배치되는 경우 PSTN IP 주소를 정의합니다. 이 주소는 선택한 주소 유형의 형식과 일치해야 합니다.

> [!NOTE]
> 프런트 엔드 서버에서 PSTN IP 주소 구성을 지원하기 위한 추가 NI(네트워크 인터페이스 카드) 설치는 지원되지 않습니다. 비즈니스용 Skype 서버의 지원되는 NIC 구성에 대한 자세한 내용은 [Lync Server 2013용](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)서버 하드웨어 플랫폼을 참조하세요.

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>중재 서버에 IP 주소 유형 배포

토폴로지 작성기에서 다음 절차의 단계를 수행하여 중재 서버에 IP 주소 유형을 배포합니다.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>중재 서버에 IP 주소 유형을 배포하는 경우

- 토폴로지 작성기의 **중재** 풀에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 선택합니다.** 또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.

- **속성 편집** 대화 상자에서 구성할 IP 주소 유형을 선택합니다. 이중 스택 구성의 경우 다음 그림과 같이 **IPv4 사용** 과 **IPv6 사용** 을 선택합니다.

   **중재 서버 풀의 속성 편집 대화 상자**

  - **구성된 모든 IP 주소**. 컴퓨터에 정의되어 있는 모든 IP 주소를 사용할 수 있도록 하려면 이 옵션을 선택합니다.

    > [!NOTE]
    > 이것이 IP 버전 6(IPv6) 구성에서 권장되는 옵션입니다.

  - **선택한 IP 주소로 서비스 사용 제한**. 새 서버에서 사용할 특정 주소를 지정하려면 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 기본 IP 주소의 값을 입력해야 합니다.

  - **기본 IP 주소**. 서버에서 PSTN(공중 전화망)을 제외한 모든 통신에 사용할 IP 주소를 입력합니다. 입력하는 IP 주소는 선택한 주소 유형의 형식과 일치해야 합니다.

  - **PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에 배치되는 경우 PSTN IP 주소를 정의합니다. 이 주소는 선택한 주소 유형의 형식과 일치해야 합니다.
> [!IMPORTANT]
> 전용 중재 서버에서는  두 개의 네트워크 카드만 지원됩니다. 중재 Sserver 역할이 프런트 엔드에 함께 있는 경우 이중 네트워크 카드가 지원되지 않습니다. 

> [!NOTE]
> - 비즈니스용 Skype 서버 2015의 지원되는 NIC 구성에 대한 자세한 내용은 [비즈니스용 Skype 서버 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015) 하드웨어를 참조하세요.
> - 비즈니스용 Skype 서버 2019의 지원되는 NIC 구성에 대한 자세한 내용은 [비즈니스용 Skype 서버 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019) 하드웨어를 참조하세요.



## <a name="deploy-ip-address-types-on-an-edge-server"></a>에지 서버에 IP 주소 유형 배포

토폴로지 작성기에서 다음 단계를 수행합니다.

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>에지 서버에 IP 주소 유형을 배포하는 경우

1. 토폴로지 작성기에서 에지 풀 아래에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 선택합니다.**  또흔 서버를 선택한 후 **동작** 메뉴에서 **속성 편집** 을 클릭합니다.

2. 속성 **편집** 창에서 지원할 IP 주소 구성을 선택합니다.

3. 선택한 각 주소 유형에 대해 적절한 내부 및 외부 주소를 제공해야 합니다.
