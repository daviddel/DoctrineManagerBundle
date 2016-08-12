Usage
-----

```php
// AppBundle/Entity/Content.php

use Doctrine\Manager\Mapping\Annotation as MM;
use Doctrine\ORM\Mapping as ORM;

/**
 * @ORM\Entity(repositoryClass="Doctrine\Manager\Model\ORM\EntityRepository")
 * @ORM\Table(name="content")
 * @MM\ModelManager(class="ContentBundle\Entity\Manager\ContentManager")
 */
class Content
```

```php
// AppBundle/Controller/ContentController.php

public function indexAction(Request $request)
{
    $contentManager = $this->get('manager.factory')->getManager(Content::class);
    $contents = $contentManager->getRepository()->findAll();
}
```
