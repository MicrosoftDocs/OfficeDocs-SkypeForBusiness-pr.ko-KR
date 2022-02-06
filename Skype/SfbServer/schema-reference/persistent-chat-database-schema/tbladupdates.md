---
title: tblADUpdates
ms.reviewer: null
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리되지 않은 Active Directory 도메인 서비스 변경 내용이 포함되어 있습니다.
---

# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리되지 않은 Active Directory 도메인 서비스 변경 내용이 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, null이 아님  <br/> |변경된 개체의 사용자 GUID입니다.  <br/> |
|prinADPath  <br/> |nvarchar(384), null이 아님  <br/> |개체의 고유 이름입니다.  <br/> |
|prinAttributesChanged  <br/> |bit, null이 아님  <br/> |개체의 특성이 하나 이상 변경된 경우 True입니다.  <br/> |
|prinMembersChanged  <br/> |bit, null이 아님  <br/> |구성원 자격이 변경된 경우 True입니다.  <br/> |
|prinAffiliationsChanged  <br/> |bit, null이 아님  <br/> |사용되지 않습니다.  <br/> |
|prinDeleted  <br/> |bit, null이 아님  <br/> |개체가 삭제된 경우 True입니다.  <br/> |
|lastUpdated  <br/> |datetime, null이 아님  <br/> |행이 삽입되었을 때의 타임스탬프입니다.  <br/> |
   

