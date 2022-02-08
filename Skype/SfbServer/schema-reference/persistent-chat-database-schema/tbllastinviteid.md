---
title: tblLastInviteId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId에는 각 사용자에 대해 생성(및 tblPrincipalInvites 테이블에서 사용)된 마지막 초대 ID가 포함됩니다.
ms.openlocfilehash: b81f358b4e042cd11b77b3f3e34db3819b7f7a70
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393670"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId에는 각 사용자에 대해 생성(및 tblPrincipalInvites 테이블에서 사용)된 마지막 초대 ID가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|lastInviteID  <br/> |int, null이 아님  <br/> |마지막으로 초대 ID입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|prinID  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblPrincipalInvites](tblprincipalinvites.md)
