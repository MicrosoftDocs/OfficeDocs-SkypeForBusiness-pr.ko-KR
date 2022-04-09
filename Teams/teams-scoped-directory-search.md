---
title: Teams 디렉터리를 검색할 때 사용자가 볼 수 있는 사용자 제한
author: MikePlumleyMSFT
ms.author: mikeplum
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Teams 디렉터리를 검색할 때 사용자가 볼 수 있는 사용자를 제한하는 방법을 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b073cdd67d89de7d934990abc33cb0586d0fc76
ms.sourcegitcommit: 5fe5516f6118ce3fa0449ab194a6fe87bf48c664
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2022
ms.locfileid: "64732226"
---
# <a name="limit-who-users-can-see-when-searching-the-directory-in-teams"></a>Teams 디렉터리를 검색할 때 사용자가 볼 수 있는 사용자 제한

Microsoft Teams 조직에서 디렉터리의 사용자 지정 보기를 사용자에게 제공할 수 있습니다. 이러한 보기는 다음과 같은 경우에 유용할 수 있습니다.

- 조직의 테넌트 내에 별도로 유지하려는 여러 회사가 있는 경우
- 비즈니스 정책에 따라 조직 내의 특정 그룹이 서로 통신하지 못하도록 해야 합니다.
- 학교에서 교사와 학생 간의 채팅을 제한하려고 하는 경우

사용자가 Teams 디렉터리를 검색할 때 볼 수 있는 사용자를 제한하는 두 가지 옵션이 있습니다.

- [Microsoft Teams 정보 장벽](/MicrosoftTeams/information-barriers-in-teams)
- [Exchange Online 주소록 정책](/exchange/address-books/address-book-policies/address-book-policies)

두 옵션 중 하나를 사용하는 경우 Teams 관리 센터에서 이름으로 검색을 설정해야 합니다.

조직에서 [필요한 라이선스 및 사용 권한을](/microsoft-365/compliance/information-barriers#required-licenses-and-permissions) 충족하는 경우 정보 장벽을 사용하는 것이 좋습니다.

이름으로 검색을 켜려면

1. Microsoft Teams 관리 센터에서 **Teams** >  **Teams 설정을** 선택합니다.

1. **이름으로 검색** 에서 **Exchange 주소록 정책을 사용하여 범위 디렉터리 검색** 옆에 있는 **토글을 켭** 니다.

> [!Note]
> 이 변경 내용이 적용되려면 몇 시간이 걸릴 수 있습니다.
