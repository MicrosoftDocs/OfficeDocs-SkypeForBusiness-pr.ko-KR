---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference 설정 사용자의 클라이언트 기본 설정을 포함 합니다. 이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 합니다.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196621"
---
# <a name="tblpreference"></a>tblPreference

tblPreference 설정 사용자의 클라이언트 기본 설정을 포함 합니다. 이는 일반적으로 Lync 2013 이전 클라이언트에서 사용 합니다.

**열**


| **열**            | **유형**                        | **설명**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), null 아님  <br/> | 레이블이 다음과 같은 형식으로 지정 된 \<레이블: 사용자 sip uri\>                   |
| prefSeqID  <br/>      | int, null 아님  <br/>            | 버전 관리 목적에 대 한 순차 번호 (레이블 당).  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | 인코딩된 콘텐츠  <br/>                                         |
| lastModifiedBy  <br/> | int, null 아님  <br/>            | 기본 설정을 업데이트 한 사용자의 ID입니다.  <br/>         |

**키**

|**열**|**설명**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |기본 키입니다.  <br/> |


