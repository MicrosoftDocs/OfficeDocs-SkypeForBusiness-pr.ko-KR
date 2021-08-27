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
ms.localizationpriority: medium
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference에는 사용자의 클라이언트 기본 설정이 포함되어 있습니다. 일반적으로 Lync 2013 이전의 클라이언트에서 사용됩니다.
ms.openlocfilehash: e9b4518fbe203750406fe02a3a69b04d1e45a9c1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578602"
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


