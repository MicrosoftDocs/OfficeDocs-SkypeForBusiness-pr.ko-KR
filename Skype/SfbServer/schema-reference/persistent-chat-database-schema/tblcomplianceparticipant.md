---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant에는 채널당 현재 참가자와 서버 별로 포함 됩니다.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196639"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant에는 채널당 현재 참가자와 서버 별로 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), null 아님  <br/> |채널 URI (Uniform Resource Identifier)입니다.  <br/> |
|userId  <br/> |int, null 아님  <br/> |참가자의 사용자 ID (tblPrincipal 테이블에 해당)  <br/> |
|에서 joinedAt  <br/> |bigint, null이 아님  <br/> |참가 이벤트의 타임 스탬프입니다.  <br/> |
|partedAt  <br/> |bigint  <br/> |참가자가 아직 참가 한 경우 Null입니다. Null이 아닌 경우 이벤트를 종료 하는 채널의 타임 스탬프입니다.  <br/> 이러한 항목은 모든 번역기가 이벤트를 처리할 때 결국 제거 됩니다.  <br/> |
|userUri  <br/> |nvarchar (255), null 아님  <br/> |사용자 URI입니다.  <br/> |
|serverID  <br/> |int  <br/> |서버 id (tblServerIdentity 테이블에 해당)  <br/> |
|Session  <br/> |bigint  <br/> |서버 세션. 채팅 서비스를 시작할 때마다 생성 되는 난수입니다. 고아 참가자를 식별 하기 위해 세션을 구분 하는 데 사용 됩니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |기본 키입니다.  <br/> |
   

