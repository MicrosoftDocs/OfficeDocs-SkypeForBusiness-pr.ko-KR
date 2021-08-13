---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference에는 사용자의 클라이언트 기본 설정이 포함되어 있습니다. 일반적으로 Lync 2013 이전의 클라이언트에서 사용됩니다.
ms.openlocfilehash: 698976f3f98b939578787a0f8a2c0aeb8167888ad09ea20a09d0d7e4d83e900c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315434"
---
# <a name="tblpreference"></a>tblPreference

tblPreference에는 사용자의 클라이언트 기본 설정이 포함되어 있습니다. 일반적으로 Lync 2013 이전의 클라이언트에서 사용됩니다.

**열**


| **열**            | **유형**                        | **설명**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar(255), null이 아님  <br/> | 형식을 지정하는 레이블: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, null이 아님  <br/>            | 버전 관리 목적의 일련 번호(레이블당)입니다.  <br/> |
| prefContent  <br/>    | nvarchar(max)  <br/>           | 인코딩된 콘텐츠입니다.  <br/>                                         |
| lastModifiedBy  <br/> | int, null이 아님  <br/>            | 기본 설정을 업데이트한 사용자의 ID입니다.  <br/>         |

**키**

|**열**|**설명**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |기본 키입니다.  <br/> |


