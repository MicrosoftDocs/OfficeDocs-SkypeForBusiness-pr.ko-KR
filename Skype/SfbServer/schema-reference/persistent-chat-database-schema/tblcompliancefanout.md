---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 테이블에는 준수 이벤트를 처리한 모든 서버가 포함됩니다.
ms.openlocfilehash: fdddd6bc1157e76ff94d86d6553da3a7308cd0f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420881"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout 테이블에는 준수 이벤트를 처리한 모든 서버가 포함됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |이벤트 ID입니다.  <br/> |
|fanoutServerID  <br/> |int  <br/> |서버 ID(tblServerIdentity.serverID 테이블에 해당됨)입니다.  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|fanoutEventID  <br/> |tblComplianceData.cmplEventID 테이블에서 조회 기능이 있는 외래 키입니다.  <br/> |
   

