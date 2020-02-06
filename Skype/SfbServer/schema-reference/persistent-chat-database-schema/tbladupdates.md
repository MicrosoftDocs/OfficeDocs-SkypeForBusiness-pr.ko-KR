---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 하지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814686"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 하지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID (null 아님)  <br/> |변경 된 개체의 Principal GUID입니다.  <br/> |
|prinADPath  <br/> |nvarchar (384), null 아님  <br/> |개체의 고유 이름입니다.  <br/> |
|prinAttributesChanged  <br/> |bit, null이 아님  <br/> |개체의 특성이 하나 이상 변경 된 경우 True입니다.  <br/> |
|prinMembersChanged  <br/> |bit, null이 아님  <br/> |구성원 자격이 변경 된 경우 True입니다.  <br/> |
|prinAffiliationsChanged  <br/> |bit, null이 아님  <br/> |사용 되지 않습니다.  <br/> |
|prinDeleted  <br/> |bit, null이 아님  <br/> |개체가 삭제 된 경우 True입니다.  <br/> |
|lastUpdated 됨  <br/> |datetime, null 아님  <br/> |행이 삽입 된 시간의 타임 스탬프입니다.  <br/> |
   

