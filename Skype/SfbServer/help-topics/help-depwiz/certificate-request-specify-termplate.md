---
title: 인증서 요청(템플릿 지정)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
description: 대체 인증서 템플릿 지정 페이지에서는 기본적으로 사용되는 WebServer 인증서 템플릿이 아닌 인증서 템플릿을 정의할 수 있습니다. 선택한 인증 기관에 대체 인증서 템플릿 사용 확인란을 선택한 다음 인증서 템플릿 이름 텍스트 상자에 대체 인증서 템플릿의 이름을 정의합니다. CA(인증 기관)에 정의된 대로 템플릿의 이름을 사용해야 합니다. 이전 페이지로 돌아가려면 뒤로를 클릭합니다. 인증서 요청 프로세스를 끝내려면 취소를 클릭합니다.
ms.openlocfilehash: 18617077c6e8633db5e6a05b214c922985d14898
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805128"
---
# <a name="certificate-request-specify-termplate"></a><span data-ttu-id="3e478-107">인증서 요청(템플릿 지정)</span><span class="sxs-lookup"><span data-stu-id="3e478-107">Certificate Request (Specify Termplate)</span></span>
 
<span data-ttu-id="3e478-p102">**대체 인증서 템플릿 지정** 페이지에서는 기본적으로 사용되는 WebServer 인증서 템플릿이 아닌 인증서 템플릿을 정의할 수 있습니다. **선택한 인증 기관에 대체 인증서 템플릿 사용** 확인란을 선택한 다음 **인증서 템플릿 이름** 텍스트 상자에 대체 인증서 템플릿의 이름을 정의합니다. CA(인증 기관)에 정의된 대로 템플릿의 이름을 사용해야 합니다. 이전 페이지로 돌아가려면 **뒤로** 를 클릭합니다. 인증서 요청 프로세스를 끝내려면 **취소** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e478-p102">The **Specify Alternate Certificate Template** page enables you to define a certificate template other than the WebServer certificate template that is used by default. Select the check box **Use alternate certificate template for selected certification authority**, and then define the name of the alternate certificate template in the text box **Certificate template name**. You must use the name of the template as it is defined in the certification authority (CA). Click **Back** to go back to the previous page. Click **Cancel** to end the certificate request process.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="3e478-p103">공용 CA에서 인증서 발급 시 공용 CA의 시스템에 정의된 특정 템플릿을 사용해야 한다고 권장한 경우에만 이 옵션을 사용해야 합니다. 내부 CA에서 인증서를 발급하는 경우 CA 관리자가 대체 인증서 템플릿에 사용할 이름을 알려 주어야 합니다. 이 옵션은 조직에서 새 WebServer 템플릿을 정의했으며 기본 WebServer 템플릿을 사용하지 않도록 설정한 경우에 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3e478-p103">You should use this option only if you are advised by your public CA that you should use a specific template that is defined on their system for issuing certificates. If the certificate is being issued by your internal CA, your CA administrator should advise you what name to use for the alternate certificate template. This option is extremely valuable in cases where your organization has defined a new WebServer template and has disabled the default WebServer template.</span></span> 
  

