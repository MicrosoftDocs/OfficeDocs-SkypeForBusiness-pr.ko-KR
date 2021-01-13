---
title: 비즈니스용 Skype 서버의 ConferenceMessageCount 테이블
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: 이 표의 각 레코드는 한 IM 회의에서 한 사용자를 나타내며 해당 사용자가 보낸 메시지 수를 포함합니다. 각 회의는 이 표의 여러 레코드로 표시됩니다. 각 사용자에 대해 하나의 레코드.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813278"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 ConferenceMessageCount 테이블
 
이 표의 각 레코드는 한 IM 회의에서 한 사용자를 나타내며 해당 사용자가 보낸 메시지 수를 포함합니다. 각 회의는 이 표의 여러 레코드로 표시됩니다. 각 사용자에 대한 하나의 레코드.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |회의 인스턴스의 시간입니다. **SessionIdSeq와** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |회의 인스턴스를 식별하기 위한 ID 번호입니다. **SessionIdTime과** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하세요. <br/> |
|**UserId** <br/> |int  <br/> |외계인  <br/> |Users 테이블에서 참조되는 이 사용자를 식별하는 [고유 번호입니다.](users.md)  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |이 회의 중에 이 사용자가 보낸 메시지 수입니다.  <br/> |
   

