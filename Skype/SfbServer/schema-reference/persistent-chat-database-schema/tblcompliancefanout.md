---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout에는 규정 준수 이벤트를 처리 한 모든 서버가 포함 됩니다.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814656"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout에는 규정 준수 이벤트를 처리 한 모든 서버가 포함 됩니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |이벤트 ID입니다.  <br/> |
|fanoutServerID  <br/> |int  <br/> |서버 id (tblServerIdentity. serverID 테이블에 해당)  <br/> |
   
**키**

|**열**|**설명**|
|:-----|:-----|
|fanoutEventID  <br/> |TblComplianceData에서 조회를 사용 하는 외래 키입니다.  <br/> |
   

