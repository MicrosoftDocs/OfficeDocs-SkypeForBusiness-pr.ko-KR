---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken에는 파일 전송 목적에 대 한 임시 토큰이 포함 되어 있습니다.
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196629"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken에는 파일 전송 목적에 대 한 임시 토큰이 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), null 아님  <br/> |고유 토큰 (GUID).  <br/> |
|fileTokenUserID  <br/> |int, null 아님  <br/> |파일을 전송 하는 주체의 ID입니다.  <br/> |
|fileTokenChannelID  <br/> |GUID (null 아님)  <br/> |채팅방 노드의 GUID입니다.  <br/> |
|fileTokenExpireDate  <br/> |datetime, null 아님  <br/> |만료 시간. (고정 되지 않는 한 30 분 후에 토큰이 만료 됩니다 (이 칼럼의 다음 설명 참조).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar (256)  <br/> |전송 된 파일의 URL입니다 (준수 서비스 사용).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar (256)  <br/> |전송 된 파일의 축소판 그림 URL입니다 (준수 서비스 사용).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |실제 파일 전송 작업 (준수 서비스 사용)에 대 한 타임 스탬프입니다.  <br/> |
|fileTokenComplianceIsUpload  <br/> |다소  <br/> |업로드 하는 경우 True False 인 경우 (준수 서비스 사용)  <br/> |
|fileTokenCompliancePinned  <br/> |bit, null이 아님  <br/> |토큰이 고정 되어 있으면 True입니다. 준수 서비스에서 관련 필드를 검색할 기회가 생길 때까지 테이블에 토큰을 유지 하는 데 사용 됩니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|fileToken  <br/> |기본 키입니다.  <br/> |
|fileTokenChannelID  <br/> |TblNode. nodeGuid 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

