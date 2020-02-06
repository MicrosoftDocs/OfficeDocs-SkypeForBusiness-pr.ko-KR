---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers에는 principal 구성원 자격이 포함 됩니다.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813946"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers에는 principal 구성원 자격이 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null 아님  <br/> |Principal ID.  <br/> |
|memberADPath  <br/> |nvarchar (384), null 아님  <br/> |구성원의 고유 이름입니다. 멤버가 principal (tblPrincipal 테이블) 일 필요는 없습니다.  <br/> |
   
**핵심**

|**열**|**설명**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |TblPrincipal prinID에 조회가 있는 외래 키입니다.  <br/> |
   

