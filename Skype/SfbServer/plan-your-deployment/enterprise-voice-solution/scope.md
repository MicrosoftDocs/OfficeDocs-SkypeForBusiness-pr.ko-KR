---
title: 비즈니스용 Skype 서버에서 E9-1-1 배포 범위 정의
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
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 비즈니스용 Skype 서버에서 E9-1-1 배포를 계획하는 데 필요한 Enterprise Voice.
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813428"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 E9-1-1 배포 범위 정의

비즈니스용 Skype 서버에서 E9-1-1 배포를 계획하는 데 필요한 Enterprise Voice.

E9-1-1에 대해 비즈니스용 Skype를 구성하기 전에 E9-1-1 배포를 계획해야 합니다. 이때 고려할 몇 가지 사항은 다음과 같습니다.

 **E9-1-1과 관련하여 조직의 정책 및 법적 의무는 무엇입니까?**

 PBX에 대한 E9-1-1 법적 요구 사항(E9-1-1 용어로는 MLTS(Multi-line Telephone Systems)라고 함)은 지역마다 다릅니다. 법률 팀에 문의하여 관련 지리의 비즈니스용 Skype 배포에 적용될 수 있는 의무를 이해해야 합니다.

 **엔터프라이즈 내에서 E9-1-1을 사용하도록 설정할 영역**

 선택한 위치에서 또는 전체 엔터프라이즈에서 E9-1-1을 사용하도록 설정할 수 있습니다. 예를 들어 각 지역의 지점에 대해 서로 다른 E9-1-1 요구 사항을 지정할 수도 있고 다른 국가의 사이트는 제외할 수도 있습니다.

 **분기 사이트에 E9-1-1을 배포할 방법**

 분기 사이트에 E9-1-1을 배포할 때 이해해야 하는 중요한 개념은 음성 탄성입니다. 중앙 집중식 E-9-1-1 SIP 트렁크가 발생하고 WAN이 정전된 경우 로그인하는 클라이언트가 위치 정보 서비스에서 위치를 얻거나 응급 서비스 서비스 공급자에 연결하지 못하게 될 수 있습니다. 비즈니스용 Skype는 지점에서 음성 탄력성 처리를 위한 몇 가지 전략을 제공합니다. 예를 들어, 탄력적인 데이터 네트워크가 있는 경우, 각 분기에 SIP 트렁크를 배포하거나, 정전 시 로컬 게이트웨이로 긴급 통화를 푸시합니다. 자세한 내용은 [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)을 참조하십시오.

 **네트워크 외부에서 작업하는 사용자에 대해 E9-1-1을 사용하도록 설정할지 여부**

 자동 위치 취득은 조직 네트워크 내에 있는 클라이언트에만 사용할 수 있으므로 조직에서는 오프-프레미스 동안 비즈니스용 Skype 클라이언트에서 걸은 E9-1-1 통화를 지원할지 여부를 결정해야 합니다. 예를 들어 사용자가 재택 근무 중이거나 고객 사이트에서 작업 중일 때 긴급 통화를 할 수 있도록 설정할지를 고려해야 합니다. 클라이언트가 엔터프라이즈 네트워크 외부에 있는 경우 사용자에게 위치를 선택하라는 메시지를 표시하도록 클라이언트를 구성할 수 있습니다. 그러나 사용자가 제공하는 위치는 MSAG(마스터 주소 가이드)와 비교하여 미리 유효성을 검사할 수 없기 때문에 응급 서비스 서비스 공급자 발송자는 통화를 PSAP(Public Safety Answering Point)로 라우팅하기 전에 구두로 발신자에게 위치의 유효성을 확인받아야 합니다.

> [!NOTE]
> VPN을 사용하여 조직의 네트워크에 연결하는 사용자의 비즈니스용 Skype 클라이언트는 내부 IP 주소 정보를 선택할 수 있지만 이러한 주소를 사용하여 사용자의 실제 위치를 식별할 수는 없습니다. VPN 서브넷은 위치 정보 서비스에서 제외해야 합니다.

 **해외 사이트에 대해 긴급 통화 라우팅을 제공할지 여부**

 응급 서비스 서비스 공급자가 서비스를 제공하지 않는 회사 지역(예: 다른 국가)에 대해 긴급 통화 라우팅 기능을 제공하려는 경우가 있을 수 있습니다. 이렇게 하려면 새 사이트를 만든 다음, 로컬 PSTN 게이트웨이를 통해 통화를 라우팅하는 PSTN 사용을 참조하는 음성 정책을 사이트에 할당합니다.


