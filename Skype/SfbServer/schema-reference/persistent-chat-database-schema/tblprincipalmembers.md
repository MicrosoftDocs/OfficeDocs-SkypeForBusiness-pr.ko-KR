---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers에는 사용자 구성원 자격이 포함됩니다.
ms.openlocfilehash: 4b7ab1ca644fae9d6cf3029e555c7bdaf476a3e5113634a4c73fd1778bc3a0dd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54346344"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
tblPrincipalMembers에는 사용자 구성원 자격이 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|prinID  <br/> |int, null이 아님  <br/> |사용자 ID입니다.  <br/> |
|memberADPath  <br/> |nvarchar(384), null이 아님  <br/> |구성원의 고유 이름입니다. 구성원은 tblPrincipal 테이블의 사용자일 필요가 없습니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |기본 키입니다.  <br/> |
|prinID  <br/> |tblPrincipal.prinID에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

