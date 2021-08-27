---
title: 프런트 엔드와 에지 연결
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: '각 프런트 엔드 풀에는 연결된 에지 서버 또는 에지 풀이 하나만 있습니다. 사이트에 대해 외부 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자에 대한 지원을 제공할 수 있습니다. 특정 공용 IM(인스턴트 메시징) 연결 공급자(예: Windows Live)의 사용자에 대한 지원과 익명 사용자에 대한 지원을 포함할 수 있는 페더러드 사용자에 대한 지원을 사용하도록 설정할 수도 있습니다.'
ms.openlocfilehash: 34b0cfe5fdfa7b98d37ff3a7458f3a4f4a59c534
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581412"
---
# <a name="associate-front-end-with-edge"></a>프런트 엔드와 에지 연결

각 프런트 엔드 풀에는 연결된 에지 서버 또는 에지 풀이 하나만 있습니다. 사이트에 대해 외부 사용자 액세스를 사용하도록 설정하는 경우 원격 사용자에 대한 지원을 제공할 수 있습니다. 특정 공용 IM(인스턴트 메시징) 연결 공급자(예: Windows Live)의 사용자에 대한 지원과 익명 사용자에 대한 지원을 포함할 수 있는 페더러드 사용자에 대한 지원을 사용하도록 설정할 수도 있습니다.

사이트의 모든 풀과 여러 중앙 사이트의 풀은 사용량이 에지 서버의 용량을 초과하지 않는 경우 동일한 에지 서버를 사용할 수 있습니다. 확장을 비롯한 모니터링에 대한 자세한 내용은 계획 설명서의 [외부 사용자 액세스 계획](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)을 참조하십시오. 외부 사용자 액세스를 지원하도록 토폴로지를 설계하는 방법에 대한 자세한 내용은 배포 설명서의 [에지 토폴로지 정의](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)를 참조하십시오.