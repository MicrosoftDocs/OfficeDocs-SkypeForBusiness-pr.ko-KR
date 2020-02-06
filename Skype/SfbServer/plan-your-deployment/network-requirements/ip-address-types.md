---
title: 비즈니스용 Skype에서 IP 주소 유형 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버를 구현 하기 전에 아래의 IP 주소 유형 고려 사항을 검토 합니다.'
ms.openlocfilehash: 74cb0738c7c6eb0518d8ab4ed4fae7db66921bfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802118"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>비즈니스용 Skype에서 IP 주소 유형 구성

**요약:** 비즈니스용 Skype 서버를 구현 하기 전에 아래의 IP 주소 유형 고려 사항을 검토 하세요.

토폴로지 작성기에서 구성한 토폴로지 설정을 사용 하 여 IP 주소 형식을 배포 합니다. 이 섹션에서는 프런트 엔드 서버, 중재 서버 및 Edge 서버에서 IP 주소 유형을 배포 하는 방법에 대해 설명 합니다.

## <a name="deploy-ip-address-types-on-a-front-end-server"></a>프런트 엔드 서버에 IP 주소 유형 배포

토폴로지 작성기를 사용 하 여 프런트 엔드 서버에 IP 주소 유형을 배포 하려면 다음 절차의 단계를 수행 합니다.

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>프런트 엔드 서버에 IP 주소 유형을 배포 하려면

1. **Enterprise Edition 프런트 엔드 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다. 또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.

2. **속성 편집** 대화 상자에서 구성 하려는 IP 주소 유형을 선택 합니다. 이중 스택 구성의 경우 **IPv4 사용** 및 **IPv6 사용**을 선택 합니다.

   **프런트 엔드 서버 풀의 속성 편집 대화 상자**

   - **구성 된 모든 IP 주소를 사용**합니다. 컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있도록 허용 하려면이 옵션을 선택 합니다.

     > [!NOTE]
     > 이 옵션은 IP 버전 6 (IPv6) 구성에 권장 됩니다.

   - **선택한 IP 주소로 서비스 사용량을 제한**합니다. 새 서버에서 사용할 특정 주소를 지정 하려면이 옵션을 선택 합니다. 이 옵션을 선택 하는 경우 **기본 IP 주소**에 대 한 값을 입력 해야 합니다.

   - **주 IP 주소** 서버가 PSTN (공공 교환 전화 네트워크)을 제외한 모든 통신에 사용할 IP 주소를 입력 합니다. 입력 하는 IP 주소는 선택 주소 유형의 형식과 일치 해야 합니다.

   - **PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에서 collocated 경우 PSTN IP 주소를 정의 합니다. 이 주소는 선택한 주소 유형의 형식과 일치 해야 합니다.

> [!NOTE]
> 프런트 엔드 서버의 PSTN IP 주소 구성 (또는 기타 이유)을 지원 하기 위해 추가 Nic (네트워크 인터페이스 카드)를 설치 하는 것은 지원 되지 않습니다. 비즈니스용 Skype 서버용으로 지원 되는 NIC 구성에 대 한 자세한 내용은 [Lync server 2013의 서버 하드웨어 플랫폼](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)을 참조 하세요.

## <a name="deploy-ip-address-types-on-a-mediation-server"></a>중재 서버에 IP 주소 유형 배포

토폴로지 작성기를 사용 하 여 다음 절차의 단계를 수행 하 여 중재 서버에 IP 주소 유형을 배포 합니다.

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>중재 서버에서 IP 주소 유형을 배포 하려면

- 토폴로지 작성기의 **중재 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다. 또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.

- **속성 편집** 대화 상자에서 구성 하려는 IP 주소 유형을 선택 합니다. 이중 스택 구성은 **IPv4 사용** 을 선택 하 고 다음 그림과 같이 **IPv6을 사용 하도록 설정**합니다.

   **중재 서버 풀에 대 한 속성 편집 대화 상자**

  - **구성 된 모든 IP 주소를 사용**합니다. 컴퓨터에 정의 된 모든 IP 주소를 사용할 수 있도록 허용 하려면이 옵션을 선택 합니다.

    > [!NOTE]
    > 이 옵션은 IP 버전 6 (IPv6) 구성에 권장 됩니다.

  - **선택한 IP 주소로 서비스 사용량을 제한**합니다. 새 서버에서 사용할 특정 주소를 지정 하려면이 옵션을 선택 합니다. 이 옵션을 선택 하는 경우 기본 IP 주소에 대 한 값을 입력 해야 합니다.

  - **주 IP 주소** 서버가 PSTN (공공 교환 전화 네트워크)을 제외한 모든 통신에 사용할 IP 주소를 입력 합니다. 입력 하는 IP 주소는 선택 주소 유형의 형식과 일치 해야 합니다.

  - **PSTN IP 주소**. 중재 서버가 프런트 엔드 서버에서 collocated 경우 PSTN IP 주소를 정의 합니다. 이 주소는 선택한 주소 유형의 형식과 일치 해야 합니다.
> [!IMPORTANT]
> *전용* 중재 서버에서는 2 개의 네트워크 카드만 지원 합니다. Sserver 역할이 프런트 엔드에서 collocated 되는 경우 이중 네트워크 카드는 지원 되지 않습니다. 

> [!NOTE]
> - 비즈니스용 Skype Server 2015의 지원 되는 NIC 구성에 대 한 자세한 내용은 비즈니스용 [Skype server 2015의 하드웨어](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015) 를 참조 하세요.
> - 비즈니스용 Skype Server 2019의 지원 되는 NIC 구성에 대 한 자세한 내용은 비즈니스용 [Skype server 2019의 하드웨어](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019) 를 참조 하세요.



## <a name="deploy-ip-address-types-on-an-edge-server"></a>에지 서버에 IP 주소 유형 배포

토폴로지 작성기를 사용 하 여 다음 단계를 수행 합니다.

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Edge 서버에 IP 주소 유형을 배포 하려면

1. 토폴로지 작성기의 **Edge 풀**에서 풀 내의 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 선택 합니다. 또는 서버를 선택한 다음 **작업** 메뉴에서 **속성 편집** 을 클릭 합니다.

2. **속성 편집** 창에서 지원 하려는 IP 주소 구성을 선택 합니다.

3. 선택한 각 주소 유형에 대해 적절 한 내부 및 외부 주소를 제공 해야 합니다.
