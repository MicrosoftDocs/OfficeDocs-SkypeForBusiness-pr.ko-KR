---
title: tblConfig
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig에는 몇 가지 영구 채팅 서버 지원되지 않는 구성이 한 행에 포함되어 있습니다.
ms.openlocfilehash: 344922f4ffb1cf172c154117c95491558f8e8905
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767366"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig에는 몇 가지 영구 채팅 서버 지원되지 않는 구성이 한 행에 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar(255), null이 아님  <br/> |"풀"을 포함합니다.  <br/> |
|configContent  <br/> |nvarchar(max)  <br/> |구성 콘텐츠입니다.  <br/> |
|configPoolID  <br/> |GUID, null이 아님  <br/> |데이터베이스 인스턴스의 고유한 ID입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|configLabel  <br/> |기본 키입니다.  <br/> |
   

