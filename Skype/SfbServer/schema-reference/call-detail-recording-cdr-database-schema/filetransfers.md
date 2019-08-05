---
title: FileTransfers 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 보기는 피어 투 피어 파일 전송 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196748"
---
# <a name="filetransfers-view"></a>FileTransfers 보기
 
FileTransfer 보기는 피어 투 피어 파일 전송 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
> [!NOTE]
> FileTransfers 보기에는 [Sessiondetails 보기](sessiondetails-0.md) 의 모든 열과 아래에 나열 된 열이 포함 됩니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**이름이** <br/> |nvarchar (256)  <br/> |전송 된 파일의 이름입니다.  <br/> |
|**쿠키란** <br/> |name  <br/> |모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.  <br/> |
|**사항** <br/> |다소  <br/> |TRUE 또는 NULL 일 수 있습니다. TRUE 인 경우 거부 및 취소는 NULL입니다.  <br/> |
|**거부** <br/> |다소  <br/> |TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept와 Cancel은 NULL입니다.  <br/> |
|**취소** <br/> |다소  <br/> |TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept 및 Reject는 NULL입니다.  <br/> |
   

