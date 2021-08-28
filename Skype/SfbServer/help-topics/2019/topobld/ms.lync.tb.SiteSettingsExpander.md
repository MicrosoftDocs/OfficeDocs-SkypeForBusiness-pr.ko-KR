---
title: Lync Server 사이트 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 기존 사이트의 속성을 편집하려면 다음을 수행합니다.
ms.openlocfilehash: cffb93e47d28ae85a70cbbaa70a0f1bf9285c1f3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619094"
---
# <a name="lync-server-site-settings-expander"></a>Lync Server 사이트 설정 확장기

기존 사이트의 속성을 편집하려면 다음을 수행합니다.



## <a name="site-properties"></a>사이트 속성

사이트 속성에서 사이트 이름(필수), 설명(선택 사항), 구/군/시(선택 사항), 시/도(선택 사항) 및 국가/지역 코드(선택 사항)를 변경 또는 수정할 수 있습니다.

사이트 속성에 대한 자세한 내용은 [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology)를 참조하십시오.

## <a name="federation-route-properties"></a>페더레이션 경로 속성

사이트 페더레이션 경로 할당을 설정하려면 먼저 에지 서버 또는 에지 서버 풀에서 페더레이션을 사용하도록 설정해야 합니다. 에지 서버 또는 풀에서 페더레이션을 사용하도록 설정하지 않은 경우 사이트의 페더레이션 경로 할당 설정을 수정할 수 없습니다.

에지 서버 또는 풀에서 페더레이션 설정을 구성한 경우 사이트 수준에서 **사용** 을 선택합니다. 그런 다음 드롭다운 목록에서 페더레이션 경로로 설정할 에지 또는 디렉터를 선택합니다.

> [!CAUTION]
> 이 설정은 모든 사이트에 영향을 미칩니다. 이 사이트에서 구성하는 설정이 모든 사이트에 대해 적합해야 합니다.

## <a name="see-also"></a>참고 항목

자세한 내용은 [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access)를 참조하십시오.