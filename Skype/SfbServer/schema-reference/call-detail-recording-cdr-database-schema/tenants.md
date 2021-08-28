---
title: Tenants 테이블
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants 테이블은 다양한 테넌트 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 테넌트를 나타냅니다.
ms.openlocfilehash: 2705b44830efef4a8f921bf9ccc9c7b8e49f72ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583792"
---
# <a name="tenants-table"></a>Tenants 테이블
 
Tenants 테이블은 다양한 테넌트 목록이 저장된 지원 테이블입니다. 테이블의 각 레코드는 하나의 테넌트를 나타냅니다.
  
> [!NOTE]
> 온-프레미스 배포의 경우 CDR은 기본 제공되는 테넌트 ID를 사용하여 공용 IM 연결, 페더레이션 및 익명과 같은 서로 다른 인증 유형을 나타냅니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |이 테넌트 ID를 식별하는 고유 번호입니다.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || 허용되는 값은 다음과 같습니다. <br/>  000000000-0000-0000-0000-0000000000000 - Enterprise <br/>  000000000-0000-0000-0000-000000000001 - 페더러 <br/>  000000000-0000-0000-0000-000000000002 - 익명 <br/>  000000000-0000-0000-0000-000000000003 - 공용 IM 연결 <br/> |
   

