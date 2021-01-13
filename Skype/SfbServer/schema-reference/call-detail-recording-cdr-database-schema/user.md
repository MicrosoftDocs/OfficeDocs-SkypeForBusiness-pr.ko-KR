---
title: 사용자 보기
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 사용자 보기에는 데이터베이스의 레코드를 포함하는 통화 또는 세션에 포함된 사용자에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831698"
---
# <a name="user-view"></a>사용자 보기
 
사용자 보기에는 데이터베이스의 레코드를 포함하는 통화 또는 세션에 포함된 사용자에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |이 사용자를 식별하는 고유 번호입니다.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |사용자의 URI입니다.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |사용자 URI의 유형입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하세요. <br/> |
   

