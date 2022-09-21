// question 2

The Model-View-Controller (MVC) is an architectural pattern that separates an application into three main logical components: the model, the view, and the controller. Each of these components are built to handle specific development aspects of an application.





// question 3





The Model
The model defines what data the app should contain. If the state of this data changes, then the model will usually notify the view (so the display can change as needed) and sometimes the controller (if different logic is needed to control the updated view).

Going back to our shopping list app, the model would specify what data the list items should contain — item, price, etc. — and what list items are already present.

The View
The view defines how the app's data should be displayed.

In our shopping list app, the view would define how the list is presented to the user, and receive the data to display from the model.

The Controller
The controller contains logic that updates the model and/or view in response to input from the users of the app.

So for example, our shopping list could have input forms and buttons that allow us to add or delete items. These actions require the model to be updated, so the input is sent to the controller, which then manipulates the model as appropriate, which then sends updated data to the view.

You might however also want to just update the view to display the data in a different format, e.g., change the item order to alphabetical, or lowest to highest price. In this case the controller could handle this directly without needing to update the model

// question 4

const path= require('path');

 const express= require('express');

 

 const productsController=require('../util/path');

 

 const rootDiv = require('.admin');

 const router=express.Router();

  router.get('/',(req, res,next)=>{

    const product = adminData.product;

    res.render('shop',{

 prods: productsController,

  pageTitle:'shop',

  path:'/',

  hasProducts: product.length >,

   activeShop:true,

    productCSS: true,



    });

  });

  



// question 5

const express= required('express');

 const bodyParser =required('body-parser');

 

 const app = express();

  const adminRouter= required('./router/admin');

   const shopRouter = required('./routes/shop');

    app.use(bodyParser.urlencoded({extended: false}));

     app.use( '/admin' ,adminRouter);

     app.use(shopRouter);





      app.use((req, res, next)=>{

        res.status(404).send(<h1>page not found</h1>);

      });

      app.listen(3000);
