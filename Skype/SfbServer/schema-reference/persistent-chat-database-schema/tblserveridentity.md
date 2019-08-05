---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity는 영구 채팅 서버 풀의 활성 채팅 서버를 포함 합니다.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196601"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity는 영구 채팅 서버 풀의 활성 채팅 서버를 포함 합니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|serverID  <br/> |int, null 아님  <br/> |서버 ID입니다. 중앙 관리 저장소의 인스턴스 ID에 해당 합니다.  <br/> |
|serverAddress  <br/> |nvarchar (256), null 아님  <br/> |Windows Communication Foundation 주소를 사용 하는 서버 주소입니다.  <br/> |
|Serverlast(Time)  <br/> |dmtf  <br/> |채널 서버가이 행을 업데이트 하 여 증거를 실행 하 고 있음을 제공 하는 최근 시간입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|serverID  <br/> |기본 키입니다.  <br/> |
   

