---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations에는 Active Directory 도메인 서비스 보안 그룹을 포함한 위치의 구성원 자격을 도메인의 Active Directory 컨테이너에 설명하는 보안 주체 회원 정보가 포함되어 있습니다.
ms.openlocfilehash: f3625a9877fffdf024131e4a0f1611018d972660
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864605"
---
# <a name="tblprincipalaffiliations"></a>tblPrincipalAffiliations
 
tblPrincipalAffiliations에는 Active Directory 도메인 서비스 보안 그룹을 포함한 위치의 구성원 자격을 도메인의 Active Directory 컨테이너에 설명하는 보안 주체 회원 정보가 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|principalID  <br/> |int, null이 아님  <br/> |연관된 사용자의 ID입니다.  <br/> |
|affiliationID  <br/> |int, null이 아님  <br/> |회원 정보를 나타내는 사용자의 ID입니다. 각 사용자(system-user-types 제외)에는 self-affiliation도 포함됩니다.  <br/> |
|index  <br/> |int, null이 아님  <br/> |인덱스입니다. 자체 소속성의 값은 -1로, 다른 소속의 경우 각 버킷 내의 1에서 1부터 일차적으로 \<principalID, affiliationId\> 증가합니다.  <br/> |
|updatedBy  <br/> |int, null이 아님  <br/> |최근 업데이트를 수행한 사용자입니다. 이 값은 일반적으로 Active Directory 동기화를 의미하는 1입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |기본 키입니다.  <br/> |
|principalID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
|affiliationID  <br/> |tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

