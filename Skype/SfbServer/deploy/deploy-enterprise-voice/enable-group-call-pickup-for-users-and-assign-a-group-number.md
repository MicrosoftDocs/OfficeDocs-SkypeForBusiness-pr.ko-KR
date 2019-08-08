---
title: 비즈니스용 Skype에서 그룹 통화 픽업으로 사용자를 설정 하 고 그룹 번호를 할당 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
description: 비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 사용자가 사용 하도록 설정 하 고 그룹 번호를 할당 합니다.
ms.openlocfilehash: 78bdd78bf7e5bb3a9438a60b54a89664d22666ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240615"
---
# <a name="enable-group-call-pickup-for-users-and-assign-a-group-number-in-skype-for-business"></a>비즈니스용 Skype에서 그룹 통화 픽업으로 사용자를 설정 하 고 그룹 번호를 할당 합니다.

비즈니스용 Skype Server Enterprise Voice에서 그룹 통화 픽업 사용자가 사용 하도록 설정 하 고 그룹 번호를 할당 합니다.

통화 번호 궤도 테이블에 통화 픽업 그룹 번호를 추가한 후에는 SEFAUtil 도구를 사용 하 여 그룹 번호를 사용자에 게 할당 하 고 그룹 통화 픽업 기능을 사용 하도록 설정 합니다.

> [!NOTE]
> 하이브리드 배포의 경우 그룹 통화 픽업 그룹을 온라인 상태인 사용자에 게 할당 하지 마세요. 홈 인터넷에 연결 된 사용자는 그룹 통화 픽업에 참가할 수 없습니다. 즉, 다른 사용자가 해당 통화에 대 한 응답을 받을 수 없으며 다른 사용자에 게 전화를 걸 수 없습니다.

### <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>그룹 번호를 할당 하 고 사용자에 대 한 그룹 통화 픽업 기능을 사용 하도록 설정 하려면

1. 관리자 권한으로 SEFAUtil 도구를 설치한 컴퓨터에 로그온 합니다.

2. 명령줄에서 다음을 실행 합니다.

   ```
   SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
   ```

    예를 들어 사용자에 게 그룹 번호 199를 할당 하려면 다음을 수행 합니다.

   ```
   SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199
   ```

## <a name="see-also"></a>참고 항목

[사용자 용 그룹 픽업 사용 안 함](https://technet.microsoft.com/library/91b06f9e-2840-45a2-bbb3-6a29179b9a9f.aspx)

