---
title: 비즈니스용 Skype 서버에서 E9-1 배포의 범위를 정의 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 비즈니스용 Skype Server Enterprise Voice에서 E9-1 배포를 계획 하는 데 필요한 결정
ms.openlocfilehash: 648713ce3474779a588d638e3e81272fbd62e2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187566"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 E9-1 배포의 범위를 정의 합니다.

비즈니스용 Skype Server Enterprise Voice에서 E9-1 배포를 계획 하는 데 필요한 결정

비즈니스용 Skype for E9-1-1을 구성 하기 전에 E9-1-1 배포를 계획 해야 합니다. 고려해 야 할 몇 가지 사항은 다음과 같습니다.

 **E9-1-1과 관련 하 여 조직의 정책 및 법적 의무는 무엇 인가요?**

 E9-1-Pbx에 대 한 법적 요구 사항 (여러 줄 전화 시스템) 또는 E9-1 parlance의 MLTS에는 state to state가 다릅니다. 해당 지역에서 비즈니스용 Skype 배포에 적용 될 수 있는 의무를 이해 하려면 법률 팀과 상의 해야 합니다.

 **E9-1-1에 대해 enterprise 내에서 어떤 영역을 사용 해야 하나요?**

 전체 enterprise 또는 선택한 위치에 대해 E9-1-1을 사용 하도록 설정할 수 있습니다. 예를 들어 서로 다른 상태의 사무실에 대해 다양 한 E9-1-1 요구 사항이 있거나 미국 외의 사이트를 제외 하려고 할 수 있습니다.

 **E9-1-1을 지사 사이트에 어떻게 배포 하나요?**

 음성 복구는 지점 사이트에서 E9-1을 구축할 때 이해 해야 하는 중요 한 개념입니다. 중앙 집중화 된 전자 9-1-1 SIP trunks을 사용 중이 고 WAN 정지가 발생 하는 경우 로그인 하는 클라이언트가 위치 정보 서비스에서 위치를 가져오지 못하거나 비상 서비스 서비스 공급자에 연결 하지 못할 수 있습니다. 비즈니스용 Skype는 회복성 있는 데이터 네트워크를 보유 하거나, 각 지점에서 SIP 트렁크를 배포 하거나, 중단 시 로컬 게이트웨이로 전화를 하는 등의 여러 가지 전략을 포함 하 여 지점에서의 음성 탄력성을 처리 합니다. 자세한 내용은 [지점 사이트 음성 복구 계획](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)을 참조 하세요.

 **네트워크 외부에서 작업 하는 사용자에 대해 E9-1-1을 사용 하도록 설정 하 시겠습니까?**

 자동 위치 취득은 조직의 네트워크 내에 있는 클라이언트에만 사용할 수 있으므로 조직에서 오프 라인 상태에서 비즈니스용 Skype 클라이언트의 E9-1 통화를 지원 하는지 여부를 결정 해야 합니다. 예를 들어 집 이나 고객 사이트에서 작업 하는 경우 사용자가 비상 전화를 걸 수 있도록 할 것인가? 클라이언트가 엔터프라이즈 네트워크 외부에 있는 경우 사용자에 게 위치를 묻는 메시지를 표시 하도록 클라이언트를 구성할 수 있습니다. 그러나 이러한 사용자 제공 위치는 MSAG (마스터 주소란)에 대해 prevalidated 수 없기 때문에 응급 서비스 서비스 공급자 발송자는 라우팅 전에 호출자와의 위치 구두로의 유효성을 확인 해야 합니다. PSAP (공개 안전 응답 시점)에 대 한 호출입니다.

> [!NOTE]
> VPN을 사용 하 여 조직의 네트워크에 연결 하는 사용자의 비즈니스용 Skype 클라이언트는 내부 IP 주소 정보를 선택할 수 있지만, 이러한 주소는 사용자의 실제 위치를 식별 하는 데 사용할 수 없기 때문에 VPN 서브넷을 제외 하는 것이 중요 합니다. 위치 정보 서비스.

 **미국 외의 사이트에 대 한 긴급 통화 라우팅을 제공 하 고 싶으세요?**

 비상 서비스 서비스 제공 업체 (예: 국제 위치)가 제공 하지 않는 회사 영역으로 긴급 라우팅 기능을 제공할 수 있습니다. 이렇게 하려면 새 사이트를 만든 다음 로컬 PSTN 게이트웨이를 통해 통화를 라우팅하는 PSTN 사용을 참조 하는 사이트에 음성 정책을 할당 합니다.


