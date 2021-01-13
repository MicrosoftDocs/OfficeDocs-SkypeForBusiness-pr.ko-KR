---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock은 일부 관리자 명령을 실행하는 데 필요한 관리자 잠금을 포함합니다.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809888"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock은 일부 관리자 명령을 실행하는 데 필요한 관리자 잠금을 포함합니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, null이 아님  <br/> |잠금 만료 날짜 및 시간입니다. 소유자는 이 값을 주기적으로 연장할 수 있습니다.  <br/> |
|lockServerID  <br/> |int, null이 아님  <br/> |잠금을 소유하는 서버의 ID입니다.  <br/> |
|lockActorID  <br/> |int, null이 아님  <br/> |잠금을 소유하는 사용자의 ID입니다.  <br/> |
   

