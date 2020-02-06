---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 되어 있습니다.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813576"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|prinAffiliationsDirty  <br/> |bit, null이 아님  <br/> |Principal 소속을 새로 고쳐야 하는 경우 True입니다.  <br/> |
|prinAttributesDirty  <br/> |bit, null이 아님  <br/> |Principal 특성을 새로 고쳐야 하는 경우 True입니다.  <br/> |
|prinDeleted  <br/> |bit, null이 아님  <br/> |보안 주체가 삭제 된 경우 True입니다.  <br/> |
|tryCount  <br/> |int  <br/> |지금까지 발생 한 AD DS에서 보안 주체의 새로 고침 시도 횟수입니다.  <br/> |
|lastTry  <br/> |dmtf  <br/> |주 사용자를 새로 고치기 위한 최신 시도의 타임 스탬프입니다. 아직 새로 고침이 시도 되지 않은 경우 null이 될 수 있습니다.  <br/> |
|nextTry  <br/> |dmtf  <br/> |예정 된 다음 새로 고침에 대 한 타임 스탬프입니다. 추가 새로 고침이 예약 되지 않은 경우 null이 될 수 있습니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|prinID  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

