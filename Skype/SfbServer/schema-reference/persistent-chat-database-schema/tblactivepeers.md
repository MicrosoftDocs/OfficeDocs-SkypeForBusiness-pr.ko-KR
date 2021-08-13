---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함되어 있습니다.
ms.openlocfilehash: 7ba8bb5730dc1c08a3d0f8aa13d1173192b7cc65134d90c75061ede0db5aa98d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336398"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, null이 아님  <br/> |항목을 게시한 서버의 ID입니다.  <br/> |
|aplPeerID  <br/> |int, null이 아님  <br/> |게시 서버가 연결된 피어의 ID입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |기본 키입니다.  <br/> |
|aplServerID  <br/> |tblServerIdentity.serverID 테이블에서 lookup이 있는 외장 키입니다.  <br/> |
|aplPeerID  <br/> |tblServerIdentity.serverID 테이블에서 lookup이 있는 외장 키입니다.  <br/> |
   

