---
title: UserAgent 보기
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent 보기는 데이터베이스에 레코드가 있는 세션과 관련 된 사용자 에이전트에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805086"
---
# <a name="useragent-view"></a>UserAgent 보기
 
UserAgent 보기는 데이터베이스에 레코드가 있는 세션과 관련 된 사용자 에이전트에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |이 사용자 에이전트를 식별 하는 고유 번호입니다.  <br/> |
|UserAgent  <br/> |nvarchar (256)  <br/> |사용자 에이전트 문자열입니다.  <br/> |
|UAType  <br/> |smallint  <br/> |사용자 에이전트의 유형입니다. 자세한 내용은 [UserAgent 테이블](useragent.md) 을 참조 하세요. <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |사용자 에이전트가 속한 범주입니다. 예를 들어 사용자 에이전트 Conferencing_Attendant_1 .0는 UACategory CAA에 속합니다.  <br/> |
   

