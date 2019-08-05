---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId에는 각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)가 포함 되어 있습니다.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196625"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId에는 각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)가 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|lastInviteID  <br/> |int, null 아님  <br/> |마지막으로 사용한 초대 ID입니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|prinID  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   
## <a name="see-also"></a>참고 항목

[tblPrincipalInvites](tblprincipalinvites.md)
