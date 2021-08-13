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
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315424"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState에는 풀 전체 준수 상태 정보가 포함되어 있습니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, null이 아님  <br/> |처리된 최신 준수 이벤트의 ID입니다.  <br/> |
|activeServerID  <br/> |int, null이 아님  <br/> |데이터베이스에 대한 단독 잠금을 보유하는 준수 서버의 ID 또는 없음인 경우 -1입니다.  <br/> |
|lockExpirationTime  <br/> |datetime2, null이 아미기  <br/> |잠금 만료 시간(activeServerID가 -1이 아닌 경우)  <br/> |
   

