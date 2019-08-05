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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig에는 일부 영구 채팅 서버에서 지원 되지 않는 구성이 한 행에 포함 되어 있습니다.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196636"
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
   

