---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814626"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), null 아님  <br/> |"Pool"를 포함 합니다.  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |구성 콘텐츠.  <br/> |
|configPoolID  <br/> |GUID (null 아님)  <br/> |데이터베이스 인스턴스의 고유 ID입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|configLabel  <br/> |기본 키입니다.  <br/> |
   

