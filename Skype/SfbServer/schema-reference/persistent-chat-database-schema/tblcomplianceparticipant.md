---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant에는 채널 및 서버별 현재 참가자가 포함됩니다.
ms.openlocfilehash: 4da7a5511caba65dc1ab4027647bed3262601dd4ef2e35949ae0bc0978451145
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351927"
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
   

