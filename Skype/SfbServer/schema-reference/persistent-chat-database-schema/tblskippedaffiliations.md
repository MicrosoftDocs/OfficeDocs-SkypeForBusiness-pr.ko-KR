---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations에는 읽을 수 없는 소속 (일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해)이 포함 됩니다.
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812016"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations에는 읽을 수 없는 소속 (일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해)이 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|affDescription  <br/> |nvarchar (256), null 아님  <br/> |소속을 식별 하는 문자열입니다.  <br/> 형식: guid: _{0}_ uri: _{1}_> id:_{2}_ <br/> |
|updatedBy  <br/> |int, null 아님  <br/> |이 행을 업데이트 한 사용자의 ID입니다. Active Directory 동기화가 이러한 항목에 대 한 유일한 원본 이므로 항상 1 (시스템 사용자)입니다.  <br/> |
   
**핵심**

|**개 열**|**설명**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

