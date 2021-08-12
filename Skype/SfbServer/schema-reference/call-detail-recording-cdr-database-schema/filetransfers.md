---
title: FileTransfers 보기
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 보기에는 피어 투 피어 파일 전송 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: e805b770038eb7fae93337c5d6c26d7059e5764436328f6321e65c948e40c88d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349690"
---
# <a name="filetransfers-view"></a>FileTransfers 보기
 
FileTransfer 보기에는 피어 투 피어 파일 전송 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
> [!NOTE]
> FileTransfers 보기에는 [SessionDetails](sessiondetails-0.md) 보기의 모든 열과 아래에 나열된 열이 포함되어 있습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**FileName** <br/> |nvarchar(256)  <br/> |전송된 파일의 이름입니다.  <br/> |
|**쿠키** <br/> |nvarchar(128)  <br/> |이 항목과 연결 중인 모든 후속 작업 메시지를 식별하기 위해 사용됩니다.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |동일한 파일 이름을 포함하는 각 전송 작업을 구분하기 위한 고유 식별자입니다.  <br/> |
|**수락** <br/> |bit  <br/> |TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Reject 및 Cancel이 NULL이 됩니다.  <br/> |
|**거부** <br/> |bit  <br/> |TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Cancel이 NULL이 됩니다.  <br/> |
|**취소** <br/> |bit  <br/> |TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Reject가 NULL이 됩니다.  <br/> |
   

