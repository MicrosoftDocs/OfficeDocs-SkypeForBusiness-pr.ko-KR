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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState에는 풀 전체 준수 상태 정보가 포함되어 있습니다.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809728"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState에는 풀 전체 준수 상태 정보가 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, null이 아님  <br/> |처리된 최신 준수 이벤트의 ID입니다.  <br/> |
|activeServerID  <br/> |int, null이 아님  <br/> |데이터베이스에 대한 배타적 잠금을 보유하는 준수 서버의 ID 또는 없음인 경우 -1입니다.  <br/> |
|lockExpirationTime  <br/> |datetime2, null이 아닌  <br/> |잠금 만료 시간(activeServerID가 -1이 아닌 경우)  <br/> |
   

