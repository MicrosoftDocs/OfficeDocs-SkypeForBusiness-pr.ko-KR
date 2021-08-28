---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState에는 풀 전체 준수 상태 정보가 포함되어 있습니다.
ms.openlocfilehash: c96f43c27179d5dd933aeba7f1483be3e1f7ee7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580402"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState에는 풀 전체 준수 상태 정보가 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, null이 아님  <br/> |처리된 최신 준수 이벤트의 ID입니다.  <br/> |
|activeServerID  <br/> |int, null이 아님  <br/> |데이터베이스에 대한 단독 잠금을 보유하는 준수 서버의 ID 또는 없음인 경우 -1입니다.  <br/> |
|lockExpirationTime  <br/> |datetime2, null이 아미기  <br/> |잠금 만료 시간(activeServerID가 -1이 아닌 경우)  <br/> |
   

