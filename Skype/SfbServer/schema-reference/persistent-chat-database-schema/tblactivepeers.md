---
title: tblActivePeers
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함되어 있습니다.
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
   

