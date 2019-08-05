---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함 되어 있습니다.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196652"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
tblActivePeers에는 채팅 서비스 간의 현재 피어 투 피어 연결이 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, null 아님  <br/> |항목을 게시 한 서버의 ID입니다.  <br/> |
|aplPeerID  <br/> |int, null 아님  <br/> |게시 서버가 연결 된 피어의 ID입니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |기본 키입니다.  <br/> |
|aplServerID  <br/> |TblServerIdentity 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
|aplPeerID  <br/> |TblServerIdentity 테이블에 조회를 포함 하는 외래 키입니다.  <br/> |
   

