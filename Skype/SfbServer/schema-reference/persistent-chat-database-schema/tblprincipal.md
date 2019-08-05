---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: tblPrincipal 사용자, 폴더 및 그룹을 비롯 한 모든 사용자를 포함 합니다.
ms.openlocfilehash: 5a0b6535ace344951b75f7c5c9488f56a18564ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196620"
---
# <a name="tblprincipal"></a>tblPrincipal
 
tblPrincipal 사용자, 폴더 및 그룹을 비롯 한 모든 사용자를 포함 합니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|prinGuid  <br/> |GUID (null 아님)  <br/> |Principal GUID. 이는 해당 의미가 Active Directory 도메인 서비스 공간으로 교차 되므로 대체 기본 키로 광범위 하 게 사용 됩니다. (캐시 된 보안 주체의 GUID는 해당 Active Directory 개체 GUID와 같습니다.)  <br/> |
|prinUri  <br/> |nvarchar (256), null 아님  <br/> |Principal URI. SIP 스키마는 사용자에 게 사용 되며 ma는 거의 모든 내용에 사용 됩니다.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |일반 이름입니다. 사용자 유형별로만 사용 됩니다.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |표시 이름입니다. 사용자 유형별로만 사용 됩니다.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |회사 이름입니다. 사용자 유형별로만 사용 됩니다.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |메일 주소. 사용자 유형별로만 사용 됩니다.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |주체가 캐시 된 버전인 Active Directory 개체의 도메인 이름입니다. Active Directory 개체 (예: 시스템 사용자)가 아닌 형식의 경우 Null이 될 수 있습니다.  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |사용자의 UPN (사용자 계정 이름). 일반 사용자 형식 으로만 사용 됩니다.  <br/> |
|prinDisabled  <br/> |smallint, null이 아님  <br/> | 0: 주체가 활성 상태입니다. <br/>  1: 사용자의 SIP 접근 권한 값을 사용할 수 없기 때문에 Principal을 사용할 수 없습니다. <br/>  2: 연결 된 광고 개체가 삭제 되어 주체가 삭제 되었습니다. <br/> |
|prinTypeID  <br/> |smallint, null이 아님  <br/> |Principal type (tblPrincipalType 테이블에서)  <br/> |
|prinPoolID  <br/> |Int  <br/> |주도자에 대 한 비즈니스용 Skype 클라이언트 풀 할당입니다.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |태그 유형 정책이 있는 경우 사용자에 대 한 영구 채팅 서버 정책 값  <br/> |
|prinAddedBy  <br/> |int  <br/> |작성자의 사용자 ID입니다.  <br/> |
|prinAddedOn  <br/> |bigint, null이 아님  <br/> |만든 시간에 대 한 타임 스탬프입니다.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |이를 마지막으로 업데이트 한 사용자의 ID입니다.  <br/> |
|prinUpdatedOn  <br/> |bigint, null이 아님  <br/> |마지막 업데이트에 대 한 타임 스탬프입니다.  <br/> |
|prinVerifiedOn  <br/> |datetime, null 아님  <br/> |주도자에 대 한 마지막 Active Directory 동기화 새로 고침의 날짜 및 시간입니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|prinID  <br/> |기본 키입니다.  <br/> |
|prinTypeID  <br/> |TblPrincipalType에 조회를 포함 하는 외래 키입니다.  <br/> |
   

