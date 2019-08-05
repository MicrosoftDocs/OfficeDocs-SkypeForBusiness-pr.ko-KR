---
title: Tenants 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 테 넌 트 테이블은 다양 한 테 넌 트 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 테 넌 트를 나타냅니다.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196678"
---
# <a name="tenants-table"></a>Tenants 테이블
 
테 넌 트 테이블은 다양 한 테 넌 트 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 테 넌 트를 나타냅니다.
  
> [!NOTE]
> 온-프레미스 배포에서 CDR는 빌드에 테 넌 트 ID를 사용 하 여 공용 IM 연결, 페더레이션 및 익명 등의 다른 인증 유형을 나타냅니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |주요한  <br/> |이 테 넌 트 ID를 식별 하는 고유 번호입니다.  <br/> |
|**TenantKey** <br/> |nvarchar (256)  <br/> || 허용 되는 값: <br/>  00000000-0000-0000-0000-000000000000-엔터프라이즈 <br/>  00000000-0000-0000-0000-000000000001-페더레이션 <br/>  00000000-0000-0000-0000-000000000002-익명 <br/>  00000000-0000-0000-0000-000000000003-공용 메신저 연결 <br/> |
   

