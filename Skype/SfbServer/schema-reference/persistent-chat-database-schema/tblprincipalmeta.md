---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 계정이 포함되어 있습니다.
ms.openlocfilehash: 77c260f56fe2f3e5b61956808b26bef1c7cf8827
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398622"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 계정이 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|prinAffiliationsDirty  <br/> |bit, null이 아님  <br/> |사용자 회원 정보를 새로 고쳐야 하는 경우 True입니다.  <br/> |
|prinAttributesDirty  <br/> |bit, null이 아님  <br/> |사용자 특성을 새로 고쳐야 하는 경우 True입니다.  <br/> |
|prinDeleted  <br/> |bit, null이 아님  <br/> |사용자가 삭제된 경우 True입니다.  <br/> |
|tryCount  <br/> |int  <br/> |지금까지 AD DS에서 사용자를 새로 고치려는 시도가 발생한 횟수입니다.  <br/> |
|lastTry  <br/> |datetime  <br/> |사용자를 새로 고치려는 가장 최근 시도의 타임스탬프입니다. 새로 고침이 아직 시도되지 않은 경우 Null일 수 있습니다.  <br/> |
|nextTry  <br/> |datetime  <br/> |다음 예약된 새로 고침의 타임스탬프입니다. 이후 새로 고침이 예약되지 않은 경우 Null일 수 있습니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|prinID  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

