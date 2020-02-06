---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations active directory 컨테이너에서 Active Directory 도메인 서비스 보안 그룹을 포함 한 위치의 구성원 자격을 도메인에 설명 하는 주요 소속을 포함 합니다.
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814476"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations active directory 컨테이너에서 Active Directory 도메인 서비스 보안 그룹을 포함 한 위치의 구성원 자격을 도메인에 설명 하는 주요 소속을 포함 합니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|principalID  <br/> |int, null 아님  <br/> |관련 된 사용자의 ID입니다.  <br/> |
|affiliationID  <br/> |int, null 아님  <br/> |소속을 나타내는 주체의 ID입니다. 각 주도자 (시스템-사용자 유형 제외)에는 자기 관련 된 것도 있습니다.  <br/> |
|색인  <br/> |int, null 아님  <br/> |색인. 자기 소속에 대 한 값은-1 이며, 다른 소속은 각 \<principalid, affiliationId\> 버킷에 있는 1에서 순차적으로 증가 합니다.  <br/> |
|updatedBy  <br/> |int, null 아님  <br/> |최신 업데이트를 수행한 보안 주체입니다. 이는 일반적으로 Active Directory 동기화를 의미 하는 1입니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |기본 키입니다.  <br/> |
|principalID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
|affiliationID  <br/> |TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

