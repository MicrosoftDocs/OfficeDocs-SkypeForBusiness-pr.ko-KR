---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock 일부 관리자 명령을 실행 하는 데 필요한 관리자 잠금을 포함 합니다.
ms.openlocfilehash: ccdc2b2667dee4d1d82a583ef7e7698d3107651a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196648"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock 일부 관리자 명령을 실행 하는 데 필요한 관리자 잠금을 포함 합니다.
  
**열**

|**열**|**유형**|**설명**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, null 아님  <br/> |잠금 만료 날짜 및 시간입니다. 소유자는이 값을 정기적으로 확장할 수 있습니다.  <br/> |
|lockServerID  <br/> |int, null 아님  <br/> |잠금을 소유 하는 서버의 ID입니다.  <br/> |
|lockActorID  <br/> |int, null 아님  <br/> |잠금을 소유 하는 주체의 ID입니다.  <br/> |
   

