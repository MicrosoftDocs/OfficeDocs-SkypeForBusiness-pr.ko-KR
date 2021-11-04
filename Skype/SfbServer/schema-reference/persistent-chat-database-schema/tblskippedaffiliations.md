---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations에는 읽지 못했습니다(일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해).
ms.openlocfilehash: 49272b03ae8ac4a3c53ea2cd99d2ed06a30c0682
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749747"
---
# <a name="tblskippedaffiliations"></a>tblSkippedAffiliations
 
tblSkippedAffiliations에는 읽지 못했습니다(일반적으로 Active Directory 도메인 서비스 액세스 오류로 인해).
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|affDescription  <br/> |nvarchar(256), null이 아님  <br/> |회원 정보를 식별하는 문자열입니다.  <br/> 형식은 guid:  _{0}_ uri:> _{1}_ ID입니다.  _{2}_ <br/> |
|updatedBy  <br/> |int, null이 아님  <br/> |이 행을 업데이트한 사용자의 ID입니다. 이러한 항목에 대해서는 Active Directory 동기화가 유일한 소스이므로 이 값은 항상 1(시스템 사용자)입니다.  <br/> |
   
**키**

|**Column(s)**|**설명**|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

