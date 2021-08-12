---
title: AV MCU와 프런트 엔드 연결
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
description: A/V 회의에서는 사용자 간의 실시간 오디오 및 비디오 통신이 가능합니다(사용자에게 오디오 회의를 위한 헤드셋, 비디오 회의를 위한 웹캠 등의 적절한 클라이언트 장치가 있는 경우). 배포에서 회의를 지원하고 사용자가 웹 회의 및 A/V 회의를 둘 다 사용하도록 설정하는 경우 프런트 엔드 서버와 함께 A/V 회의 서버를 배치하거나 하나 이상의 독립 실행형 A/V 회의 서버(A/V 회의 풀)를 배포할 수 있습니다. 독립 실행형 A/V 회의 서버를 배포하는 옵션을 선택하는 경우 토폴로지 작성기에서 정의해야 합니다.
ms.openlocfilehash: fde2801d7894a7525074b8e6cda64bda93e4ce9346d8f78325c2615e55e7ee82
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298308"
---
# <a name="associate-front-end-with-av-mcu"></a>AV MCU와 프런트 엔드 연결
 
A/V 회의에서는 사용자 간의 실시간 오디오 및 비디오 통신이 가능합니다(사용자에게 오디오 회의를 위한 헤드셋, 비디오 회의를 위한 웹캠 등의 적절한 클라이언트 장치가 있는 경우). 배포에서 회의를 지원하고 사용자가 웹 회의 및 A/V 회의를 둘 다 사용하도록 설정하는 경우 프런트 엔드 서버와 함께 A/V 회의 서버를 배치하거나 하나 이상의 독립 실행형 A/V 회의 서버(A/V 회의 풀)를 배포할 수 있습니다. 독립 실행형 A/V 회의 서버를 배포하는 옵션을 선택하는 경우 토폴로지 작성기에서 정의해야 합니다.
  
사이트의 모든 풀과 여러 중앙 사이트의 풀은 사용량이 A/V 회의 서버의 용량을 초과하지 않는 경우 동일한 A/V 회의 서버를 사용할 수 있습니다. 
  

