---
title: tblServerIdentity
ms.reviewer: ''
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity에는 영구 채팅 서버 풀의 활성 채팅 서버가 포함되어 있습니다.
ms.openlocfilehash: 0207871100904af348b4c1a51ed2c6f4574249d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398612"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity에는 영구 채팅 서버 풀의 활성 채팅 서버가 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|serverID  <br/> |int, null이 아님  <br/> |서버 ID입니다. 중앙 관리 저장소의 인스턴스 ID에 해당합니다.  <br/> |
|serverAddress  <br/> |nvarchar(256), null이 아님  <br/> |Windows Communication Foundation 주소를 사용 중인 서버 주소입니다.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |실행 중임에 대한 증거를 제공하기 위해 채널 서버가 이 행을 마지막으로 업데이트한 시간입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|serverID  <br/> |기본 키입니다.  <br/> |
   

