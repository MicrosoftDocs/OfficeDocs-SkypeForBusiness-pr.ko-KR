---
title: 전화 회선 ID 및 발신자 이름에 대한 자세한 정보
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 새 로컬 번호 포트 주문 마법사를 사용할 때 계정을 변경할 수 있는 권한이 부여된 사람을 추가해야 하는 이유를 배워야 합니다.
ms.openlocfilehash: db64a5d1a7e7a5969f66d67d6b056ec6947d44bb
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255401"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>전화 회선 ID 및 발신자 이름에 대한 자세한 정보

CallerID는 일반적으로 참조되는 두 가지 사용자 식별 정보로 구성됩니다.
    - 전화 번호(일반적으로 CLID 또는 전화 회선 ID라고도 합니다. 
    - 최대 15자까지 사용할 수 있는 파티 이름(일반적으로 CNAM이라고도 합니다)입니다. 

호출이 이루어지는 경우 CLID(전화 번호)는 대상의 통신 사업자(종료 통신 사업자라고도함)로 라우팅됩니다. 호출에 대한 CNAM 정보는 국가가 CNAM을 구현한 방식에 따라 달라지기 때문에 호출과 함께 라우팅되거나 라우팅되지 않을 수 있습니다. 통화를 사용하는 CNAM 배달의 안정성은 중개자 및/또는 종료 통신사로 통화를 처리하는 국가 및 통신 사업자에 따라 다릅니다. 

CLID & CNAM 전송은 종료 통신 사업자는 CLID & CNAM 기능을 지원하고 두 값 모두에 대한 최신 레코드를 제공해야 하기 때문에 통신 사업자는 서비스를 종료할 책임이 있습니다. Microsoft는 호출을 시작할 때 CLID 값을 안정적으로 제공하지만 중간 통신 사업자 또는 종료 통신 사업자에 전달한 후 해당 값은 그대로 유지되지 않을 수 있습니다. 안타깝게도 CLID 값이 중간 통신 회사 또는 통신 회사에 의해 변경, 생략 또는 소진될 경우 Microsoft는 공용 전화 네트워크에서 이러한 문제를 수정하는 데 거의 사용할 수 없습니다.

CNAM의 불일치는 미국의 경우와 같은 권한이 있는 데이터베이스에서 CNAM 정보를 새로 고치거나 중간 이동 통신 사업자를 종료하는 지연으로 인해 발생할 수 있습니다. CNAM에 대한 권한이 있는 데이터베이스가 없는 국가에서 개별 통신 사업자 사례로 인해 CNAM 정보가 통화와 함께 그대로 도착하는 문제도 발생할 수 있습니다. Microsoft는 현재 미국이 아닌 국가에서 CNAM 정보를 시작하지 않습니다."

## <a name="related-topics"></a>관련 항목


