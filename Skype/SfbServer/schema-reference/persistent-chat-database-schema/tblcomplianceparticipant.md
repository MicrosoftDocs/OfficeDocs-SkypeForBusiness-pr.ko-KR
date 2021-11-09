---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant에는 채널 및 서버별 현재 참가자가 포함됩니다.
ms.openlocfilehash: d28b81d6ce0169999297dbcde65b1d7fbde38780
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854072"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant에는 채널 및 서버별 현재 참가자가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar(255), null이 아님  <br/> |채널 URI(Uniform Resource Identifier)입니다.  <br/> |
|userId  <br/> |int, null이 아님  <br/> |참가자의 계정 ID(tblPrincipal.prinID 테이블에 해당됨)입니다.  <br/> |
|joinedAt  <br/> |bigint, null이 아님  <br/> |참가 이벤트의 타임스탬프입니다.  <br/> |
|partedAt  <br/> |bigint  <br/> |참가자가 아직 참가된 상태이면 Null입니다. Null이 아닌 경우 채널 나가기 이벤트의 타임스탬프입니다.  <br/> 모든 변환기에서 이벤트를 처리하면 이러한 항목이 결국 제거됩니다.  <br/> |
|userUri  <br/> |nvarchar(255), null이 아님  <br/> |사용자 URI입니다.  <br/> |
|serverID  <br/> |int  <br/> |서버 ID(tblServerIdentity.serverID 테이블에 해당됨)입니다.  <br/> |
|sessionId  <br/> |bigint  <br/> |서버 세션입니다. 이 값은 채팅 서비스가 시작할 때마다 생성되는 임의의 숫자입니다. 고립된 참가자를 식별하기 위한 목적으로 세션을 구분하기 위해 사용됩니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |기본 키입니다.  <br/> |
   

