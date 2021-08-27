---
title: 전화 회선 ID 및 발신자 이름에 대한 자세한 정보
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 전화선 ID 및 통화 파티 이름에 대해 자세히 알아보습니다.
ms.openlocfilehash: 13167e41a5e104e198c557af90ed121e90abcf55
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617244"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a>전화 회선 ID 및 발신자 이름에 대한 자세한 정보

CallerID는 다음과 같은 두 가지 사용자 관련 정보로 구성됩니다.

- 전화 번호(일반적으로 CLID 또는 전화 회선 ID라고도 합니다.

- 파티 이름(일반적으로 CNAM이라고도 합니다)을 호출합니다. 

통화가 이루어지면 CLID(전화 번호)가 대상의 통신사(종료 이동통신사라고도도)로 라우팅됩니다. 이 정보는 국가가 CNAM을 구현한 방식(있는 경우)에 따라 달라지기 때문에 호출에 대한 CNAM 정보가 호출로 라우팅되거나 라우팅되지 않을 수 있습니다. 호출을 사용하는 CNAM 배달의 안정성은 통화를 처리하는 국가 및 통신 사업자에 따라 다릅니다. 중개자 또는 종료 이동통신사입니다. 

CLID & CNAM 전송은 종료 캐리어의 책임입니다. 종료 캐리어는 CLID & CNAM 기능을 지원하고 두 값에 대한 최신 레코드를 제공해야 합니다. Microsoft는 호출을 시작할 때 CLID 값을 안정적으로 제공하지만 중개업체 또는 종료 통신업체를 통과하면 해당 값이 그대로 유지되지 않을 수 있습니다. CLID 값이 중개자 또는 종료 통신 사업자에 의해 변경, 생략 또는 틀린 경우 Microsoft는 공용 전화 네트워크에서 이러한 문제를 해결하지 않습니다.

CNAM의 불일치는 중간 또는 종료 캐리어가 미국의 경우와 같은 권위 있는 데이터베이스의 CNAM 정보 새로 고침을 지연할 때 발생할 수 있습니다. CNAM에 대한 권한이 있는 데이터베이스가 없는 국가에서 개별 통신 사업자 사례는 호출과 함께 손상되지 않습니다. Microsoft는 현재 미국이 아닌 국가에서 시작된 CNAM 정보를 지원하지 않습니다.

## <a name="related-topics"></a>관련 주제


