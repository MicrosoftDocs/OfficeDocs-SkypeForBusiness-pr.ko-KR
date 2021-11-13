---
title: 더 안전한 메시지 사용을 위한 Teams 보안 모범 사례
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 이 문서는 Teams를 안전하게 사용하는 방법에 대한 간단한 참고자료로, 사용자의 안전한 메시지 사용 교육을 위한 일반적인 보안 모범 사례 및 팁에 대한 입문서 역할을 합니다.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909687"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Microsoft Teams 보안 모범 사례

인스턴트 메시지와 화상 회의를 통한 공동 작업 덕에 많은 업계와 학교는 팬데믹 기간 동안에도 운영을 계속할 수 있었습니다. 그러나 이러한 광범위한 규모의 온라인 실시간 공동 작업은 해결해야 하는 *위험* 을 동반합니다. 이를 해결하지 않을 경우 악의적인 행위자가 이러한 직장과 일상 생활의 변화를 **피싱** 이나 **스팸** 캠페인에 악용할 수 있습니다. 이 게시물의 번호가 매겨진 참고자료는 Teams를 사용해 메시지를 보낼 때 유념해야 할 일반적인 보안 정보에 관한 입문서이자 Teams 또는 인스턴트 메시지를 처음 접하는 사용자를 위한 보안 안내서 역할을 합니다.

전자 메일에 존재하는 것과 같은 피싱 위험이 인스턴트 메시지와 공동 작업 앱에도 존재하므로 Teams 사용자를 안전하게 지키려면 동일한 사용자 인식과 안내를 적용해야 합니다.

안심하고 서비스를 사용할 수 있도록 사용자 수준에서 몇 가지 간단한 조치를 취할 수 있습니다. 사용자는 [피싱으로부터 스스로 지키기](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44) 게시물에도 나와 있듯이 모르는 사람 또는 신원을 증명할 수 없는 사람이 보낸 링크를 클릭해서 열어서는 안 됩니다. 테넌트 관리자는 또한 외부 공격에서 스스로를 지키기 위해 [외부 액세스(페더레이션) 관리 - Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access) 관련 기업 페더레이션과 TFL(Teams for Life), Skype 상호 운용성을 비활성화할 수 있습니다.

Teams 공동 작업 기능 집합을 사용하면 메시징과 파일 공동 작업, 모임, 화이트보드, 그리고 그 외 다양한 기회에 연결할 수 있습니다. 이러한 기능은 기업용 Teams, Teams for Life, Skype, 비즈니스용 Skype ACS(Azure Communication Services) 등 전체에서 작동합니다. 즉, 이러한 기능 모두에서 자신과 동료, 고객을 안전하게 지키는 게 중요합니다. 여기서도 모든 사용자가 자신과 동료, 고객에게 가장 안전한 결정을 내릴 수 있어야 합니다.

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>전자 메일과 마찬가지로 Microsoft Teams 메시지에서도 온라인 안전을 수행해야 합니다.

Teams로 작업하는 동안 표준 안전 조치를 철저히 지켜야 합니다.

1. 조직 외부의 연락처와 모임 요청에 유의해야 합니다. 낯선 사람이라고 모두 악의를 가지는 건 아니지만 일부는 몰래 나쁜 생각을 품을 수 있습니다.
2. 보낸 사람이 누군지 모르겠다면 알려진 기업 전체 주소 목록에서 신원을 확인하고, 확인할 수 없는 모든 의사소통은 상부로 에스컬레이션해서 처리합니다. 조금이라도 의심이 들면 즉시 소통을 멈추고 사용자를 확인하세요.
3. 모르는 사람에게서 링크나 파일을 받는 경우 클릭하지 마세요. 다시 말하지만 본인이 생각하기에 다른 본인과 다른 사용자, 그리고 고객의 안전에 가장 최선이라고 생각되는 선택을 하세요.
4. 링크를 클릭했을 때 탐색이 차단되는 안전한 링크로 이동하는 경우 페이지를 우회하려고 시도하지 마세요(첨부 파일을 클릭했을 때 빨간색 안전 첨부 파일 차단 페이지로 이동하는 경우에도 마찬가지입니다). 대상 사이트를 알고 신뢰하는 경우 문제를 Microsoft와 해당 사이트로 가는 경로를 제공한 당사자에게 보고하세요. 차단 페이지가 표시되는 이유는 다양하며, 경고 신호를 마주칠 시 우회하려고 하기 보다는 경위를 살펴야 합니다.
5. 일방적으로 전달된 요청에 절대 개인 정보를 제공하지 마세요. 개인 안전에도 위험한 부분입니다. 공격자는 생년월일만큼 간단한 세부 정보도 활용할 수 있습니다.
6. 링크에 수상한 맞춤법이나 추가된 숫자, 이상한 문자가 있지는 않은지 확인하세요. `www.litware.com/strategies/Metricsbreakout.xlsx`여야 할 링크 주소가 `www.litwre.com`, `www.litwarecom.com`, `www.litwαre.com` 등으로 표기되었을 수 있습니다. 모르는 링크라면 일단 의심하세요. `www.litware.com`은(는) `www.litware2021.com`와(과) 다른 주소입니다.

항상 경계하고, 본인과 함께 일하는 사람의 보안을 가볍게 여기거나 당연하게 여기지 않는 것이 중요합니다. 개별 사용자는 항상 신뢰하기 전에 검증을 통해 본인과 동료, 고객의 안전을 지킬 수 있다는 확신을 가져야 합니다.

마지막으로 누구나 실수를 할 수 있다는 사실을 인정하는 것이 중요합니다. 예를 들어 급하게 서둘러야 하는 경우나 피곤할 때 사용자는 쉽게 클릭하는 경향이 있습니다. 관리자는 실수가 발생할 경우 사용자가 리소스를 사용할 수 있고, 나아가 필요한 조치를 취할 수 있도록 문제가 있는 링크 클릭이나 기타 보안 인시던트 발생 에스컬레이션 관련 리소스 정보를 조직의 사용자에게 명확하게 전달해야 합니다.

> [!TIP]
> 확신이 없는 모든 프로필 카드, 특히 회사 외부 전자 메일을 사용하는 프로필 카드를 확인하세요(예: 조직이 *Litware* 가 아닌데 *@litware.com* 으로 끝나는 계정). 사용자는 프로필 카드에서 **(게스트)** 를 찾아 사용자가 모임에 초대된 게스트인지를 확인할 수 있습니다. 게스트는 참가 초대를 받은 사용자만을 의미합니다.