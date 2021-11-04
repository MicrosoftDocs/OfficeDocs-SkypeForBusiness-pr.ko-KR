---
title: 사용자에 대해 그룹 통화 Pickup을 사용하도록 설정하고 사용자에 대해 그룹 번호를 비즈니스용 Skype
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 사용자 그룹 통화 선택을 비즈니스용 Skype 서버 Enterprise Voice 그룹 번호를 할당합니다.
ms.openlocfilehash: c053ae4551ea5954f15261755c20afbf8a45f7b5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759091"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>사용자에 대해 그룹 통화 Pickup을 사용하도록 설정하고 사용자에 대해 그룹 번호를 비즈니스용 Skype

사용자 그룹 통화 선택을 비즈니스용 Skype 서버 Enterprise Voice 그룹 번호를 할당합니다.

통화 파킹된 통화 번호 테이블에 통화 Pickup 그룹 번호를 추가한 후 SEFAUtil 도구를 사용하여 사용자에게 그룹 번호를 할당하고 그룹 통화 Pickup을 사용하도록 설정할 수 있습니다.

> [!NOTE]
> 하이브리드 배포에서는 온라인에 있는 사용자에게 그룹 통화 선택 그룹을 할당하지 않습니다. 온라인에 있는 사용자는 그룹 통화 Pickup에 참가할 수 없습니다. 즉, 다른 사용자가 통화에 응답할 수 있으며 다른 사용자의 통화에 응답할 수 없습니다.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>그룹 번호를 할당하고 사용자에 대해 그룹 통화 선택을 사용하도록 설정하려면

1. 관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온합니다.

2. 명령줄에서 다음을 실행합니다.

   ```console
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    예를 들어 사용자에게 그룹 번호 199를 할당하는 경우:

   ```console
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>참고 항목

[사용자에 대해 그룹 선택 사용 안 하게 설정](/previous-versions/office/lync-server-2013/lync-server-2013-disable-group-call-pickup-for-users)