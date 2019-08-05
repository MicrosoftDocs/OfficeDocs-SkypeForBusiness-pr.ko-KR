---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 됩니다.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196638"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState에는 풀 전체의 준수 상태 정보가 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, null이 아님  <br/> |최근 처리 된 준수 이벤트의 ID입니다.  <br/> |
|activeServerID  <br/> |int, null 아님  <br/> |데이터베이스에 대 한 단독 잠금을 보유 하는 규정 준수 서버의 ID 이거나, 없으면-1입니다.  <br/> |
|lockExpirationTime  <br/> |datetime2, null이 아님  <br/> |잠금 만료 시간 (activeServerID가-1이 아닌 경우)  <br/> |
   

