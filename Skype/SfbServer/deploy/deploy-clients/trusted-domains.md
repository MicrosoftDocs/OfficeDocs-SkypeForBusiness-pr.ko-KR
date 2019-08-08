---
title: Skype 채팅방 시스템 신뢰할 수 있는 도메인
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Skype 채팅방 시스템 및 비즈니스용 Skype에 대해 신뢰할 수 있는 도메인을 구성 하는 방법에 대해 알아보려면이 항목을 읽으십시오.
ms.openlocfilehash: 2b2aeb98e3b1b6efe585e565c1e288d635fdb26e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235017"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="112c0-103">Skype 채팅방 시스템 신뢰할 수 있는 도메인</span><span class="sxs-lookup"><span data-stu-id="112c0-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="112c0-104">Skype 채팅방 시스템 및 비즈니스용 Skype에 대해 신뢰할 수 있는 도메인을 구성 하는 방법에 대해 알아보려면이 항목을 읽으십시오.</span><span class="sxs-lookup"><span data-stu-id="112c0-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="112c0-105">신뢰할 수 있는 도메인</span><span class="sxs-lookup"><span data-stu-id="112c0-105">Trusted domains</span></span>

<span data-ttu-id="112c0-106">비즈니스용 Skype 클라이언트는 로그인 하는 사용자 계정의 SIP 도메인이 인증서의 주체 또는 주체의 대체 이름에 표시 된 이름과 다른 경우 비즈니스용 Skype 서버에서 인증서를 수락할 수 있는 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="112c0-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="112c0-107">조직의 비즈니스용 Skype 서버용으로 구성 된 인증서가 주체 또는 주체 대체 이름에 Skype 대화방 시스템 계정의 SIP 도메인 이름을 보유 하 고 있지 않은 경우, 신뢰할 수 있는 도메인 아래의 인증서에 표시 된 해당 도메인을 구성 해야 합니다. Skype 실 시스템 콘솔 컴퓨터의 레지스트리 키입니다.</span><span class="sxs-lookup"><span data-stu-id="112c0-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="112c0-108">Skype 실 시스템 제조업체에서 제공 하는 skype 실 시스템 관리자 안내서는 비즈니스용 Skype 클라이언트에서 신뢰할 수 있는 도메인을 추가 하는 방법과 위치에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="112c0-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="112c0-109">예를 들어 비즈니스용 Skype Server에 구성 된 인증서에 "CONTOSO"의 제목/제목 대체 이름이 있다고 가정 합니다. LOCAL "과 Skype 룸 시스템 로그인 주소에 대해 사용자에 게 지정 된 SIP 도메인 중 하나가" confrm1@contoso.net "입니다.</span><span class="sxs-lookup"><span data-stu-id="112c0-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="112c0-110">Contoso.net이 인증서에 있지 않기 때문에 skype 채팅방 시스템의 경우, skype 룸 시스템 제조업체에서 설명 하는 대로 "contoso. local"을 레지스트리의 신뢰할 수 있는 도메인으로 구성 해야 합니다-skype 실 시스템 관리자 안내서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="112c0-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

