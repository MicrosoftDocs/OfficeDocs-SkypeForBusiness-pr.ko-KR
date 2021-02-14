---
title: tblFileToken
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken에는 파일 전송 목적의 임시 토큰이 포함됩니다.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816018"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken에는 파일 전송 목적의 임시 토큰이 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar(50), null이 아님  <br/> |고유한 토큰(GUID)입니다.  <br/> |
|fileTokenUserID  <br/> |int, null이 아님  <br/> |파일을 전송 중인 사용자의 ID입니다.  <br/> |
|fileTokenChannelID  <br/> |GUID, not null  <br/> |대화방 노드의 GUID입니다.  <br/> |
|fileTokenExpireDate  <br/> |datetime, null이 아님  <br/> |만료 시간입니다. 고정되지 않은 한 토큰이 30분 후 만료됩니다(이 열의 다음 설명 참조).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |전송된 파일의 URL입니다(준수 서비스용).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |전송된 파일에 대한 축소판 그림의 URL입니다(준수 서비스용).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |실제 파일 전송 작업의 타임스탬프입니다(준수 서비스용).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |업로드인 경우 True, 다운로드인 경우 False입니다(준수 서비스용).  <br/> |
|fileTokenCompliancePinned  <br/> |bit, null이 아님  <br/> |토큰이 고정된 경우 True입니다. Compliance Service에서 관련 필드를 검색할 수 있는 기회가 제공될 때까지 토큰을 테이블에 보관하는 데 사용됩니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|fileToken  <br/> |기본 키입니다.  <br/> |
|fileTokenChannelID  <br/> |tblNode.nodeGuid 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

