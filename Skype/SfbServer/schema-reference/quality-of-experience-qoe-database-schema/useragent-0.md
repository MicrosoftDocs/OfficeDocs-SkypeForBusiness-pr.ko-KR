---
title: UserAgent 보기
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 보기에는 데이터베이스에 레코드가 있는 세션에 참여한 사용자 에이전트에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: d6ed446c429c3e055d3b5387f4675eaed7fb1f9e992d7211346309254549b66d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282990"
---
# <a name="useragent-view"></a>UserAgent 보기
 
UserAgent 보기에는 데이터베이스에 레코드가 있는 세션에 참여한 사용자 에이전트에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |이 사용자 에이전트를 식별하는 고유 번호입니다.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |사용자 에이전트 문자열입니다.  <br/> |
|UAType  <br/> |smallint  <br/> |사용자 에이전트의 형식입니다. 자세한 내용은 [UserAgent 테이블을](useragent.md) 참조합니다. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |사용자가 속한 범주입니다. 예를 들어 사용자 에이전트 Conferencing_Attendant_1.0은 UACategory CAA에 속해 있습니다.  <br/> |
   

