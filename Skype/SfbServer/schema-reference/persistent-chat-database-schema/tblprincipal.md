---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal에는 사용자, 폴더 및 그룹을 비롯한 모든 참가자가 포함됩니다.
ms.openlocfilehash: 6cd47f3f58d7c68f26b5b8d35eb71db64d4d5131
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776138"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal에는 사용자, 폴더 및 그룹을 비롯한 모든 참가자가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|prinGuid  <br/> |GUID, null이 아님  <br/> |사용자 GUID입니다. 이 키는 해당 의미가 Active Directory 도메인 서비스 공간으로 교차하기 때문에 대체 기본 키로 광범위하게 사용됩니다. 캐시된 사용자의 GUID는 해당하는 Active Directory 개체 GUID와 동일합니다.  <br/> |
|prinUri  <br/> |nvarchar(256), null이 아님  <br/> |계정 URI입니다. SIP 구성표는 사용자에 대해 사용되고 ma-grp는 거의 모든 다른 항목들에 대해 사용됩니다.  <br/> |
|prinName  <br/> |nvarchar(256)  <br/> |회사 이름입니다. 사용자 유형에서만 사용됩니다.  <br/> |
|prinDisplayName  <br/> |Nvarchar(256)  <br/> |표시 이름입니다. 사용자 유형에서만 사용됩니다.  <br/> |
|prinCompanyName  <br/> |nvarchar(256)  <br/> |회사 이름입니다. 사용자 유형에서만 사용됩니다.  <br/> |
|prinEmail  <br/> |nvarchar(256)  <br/> |전자 메일입니다. 사용자 유형에서만 사용됩니다.  <br/> |
|prinADPath  <br/> |nvarchar(384)  <br/> |계정이 캐시된 버전인 Active Directory 개체의 도메인 이름입니다. Active Directory가 아닌 개체 유형의 경우 Null일 수 있습니다(예: 시스템 사용자).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar(256)  <br/> |사용자의 UPN(사용자 계정 이름) 사용자 유형에서만 사용됩니다.  <br/> |
|prinDisabled  <br/> |smallint, null이 아님  <br/> | 0: 계정이 활성입니다. <br/>  1: 사용자의 SIP 기능이 사용하지 않도록 설정되어 있기 때문에 보안 주체가 사용하지 않도록 설정됩니다. <br/>  2: 연결된 AD 개체가 삭제되었기 때문에 계정이 삭제되었습니다. <br/> |
|prinTypeID  <br/> |smallint, null이 아님  <br/> |계정 유형(tblPrincipalType 테이블)입니다.  <br/> |
|prinPoolID  <br/> |임계값  <br/> |비즈니스용 Skype 클라이언트 풀 할당을 구성합니다.  <br/> |
|prinPolicyID  <br/> |임계값  <br/> |태그 유형 정책이 있는 경우 사용자에 대한 영구 채팅 서버 정책 값입니다.  <br/> |
|prinAddedBy  <br/> |int  <br/> |작성자의 사용자 ID입니다.  <br/> |
|prinAddedOn  <br/> |bigint, null이 아님  <br/> |만든 시간에 대한 타임스탬프입니다.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |이 항목을 마지막으로 업데이트한 사용자의 ID입니다.  <br/> |
|prinUpdatedOn  <br/> |bigint, null이 아님  <br/> |마지막 업데이트에 대한 타임스탬프입니다.  <br/> |
|prinVerifiedOn  <br/> |datetime, null이 아님  <br/> |사용자에 대한 마지막 Active Directory 동기화 새로 고침의 날짜 및 시간입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|prinID  <br/> |기본 키입니다.  <br/> |
|prinTypeID  <br/> |tblPrincipalType.ptypeID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

