---
title: 2015년 8월의 IIS 요청 추적 로그 비즈니스용 Skype 서버 모니터링
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6730e92-6d74-4fa7-a83f-50b7bdadbffa
description: '요약: 레거시 클라이언트에 대한 비즈니스용 Skype 서버 2015의 Mobility Service(Mcx)에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 3a07279a099df44e72b65475af63340f27dc35d6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632882"
---
# <a name="monitoring-iis-request-tracing-log-files-in-skype-for-business-server-2015"></a>2015년 8월의 IIS 요청 추적 로그 비즈니스용 Skype 서버 모니터링
 
**요약:** 레거시 클라이언트에 대한 비즈니스용 Skype 서버(Mcx)에 대해 자세히 알아보습니다.
  
이 항목은 Lync 2010 Lync Mobile 클라이언트를 지원하는 배포에만 적용하며 Mcx(Mobility Service)를 위한 것입니다.

> [!NOTE]
> 레거시 모바일 클라이언트에 대한 MCX(Mobility Service) 지원은 2019년 8월 비즈니스용 Skype 서버 없습니다. 현재 비즈니스용 Skype 클라이언트는 이미 UCWA(Unified Communications Web API)를 사용하여 IM(인스턴트 메시징), 현재 상태 및 연락처를 지원하고 있습니다. MCX를 사용하는 레거시 클라이언트를 사용하는 사용자는 현재 클라이언트로 업그레이드해야 합니다.
  
mcx(비즈니스용 Skype 서버 Mobility Service)에 대해 IIS(인터넷 정보 서비스) 요청 추적을 사용하도록 설정하면 생성되는 로그 파일은 하루에 최대 3기가바이트의 디스크 공간을 사용할 수 있습니다. IIS 추적 로깅은 기본적으로 사용하도록 설정됩니다. 프런트 엔드 서버를 모니터링하여 디스크 공간이 모두 손실되지 않는지 확인해야 합니다. 
  
IIS에서는 로그 파일이 기본적으로 %SystemDrive%\inetpub\logs\LogFiles에 저장됩니다.
  
전체 서버에 대해 IIS 요청 추적을 해제하려면 명령줄에서 다음을 입력합니다.
  
```console
%SystemDrive%\Windows\System32\inetsrv\appcmd set config /section:httpLogging /dontLog:True
```

**httpLogging** 명령에 대한 자세한 내용은 명령 참조 [를 참조합니다.](/previous-versions/iis/settings-schema/aa347466(v=vs.90))
