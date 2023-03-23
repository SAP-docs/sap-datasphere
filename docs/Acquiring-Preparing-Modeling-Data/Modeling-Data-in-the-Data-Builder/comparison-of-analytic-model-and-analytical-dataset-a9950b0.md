<!-- loioa9950b0a7bc04fd1b9827800e67b26f1 -->

# Comparison of Analytic Model and Analytical Dataset

The analytic model is now the object for building stories on in SAP Analytics Cloud.

The analytic model will replace analytical datasets which are exposed for consumption. Analytical datasets will continue to exist, but you should now use the analytic model instead.

The analytic model offers more calculations and greater functionality. You can prune what you want to expose in your object, thus avoiding unnecessary calculations and in turn achieving a better performance. It also offers calculated measures and restricted measures, and an analytical preview.

Analytical datasets will still be available, but new features will only be developed for the analytic model. You can easily create analytic model on top of analytical datasets.

A number of terms and concepts are used differently in the analytic model. Please take a look at the following section in order to familiarize yourself with these terms.



<a name="loioa9950b0a7bc04fd1b9827800e67b26f1__section_ihs_1vx_bvb"/>

## Variables and Input Parameters

The “input parameter” in analytical datasets is known as a “variable” in analytic models. This is because we also talk about variables in the story in SAP Analytics Cloud. As the analytic model is the object for consumption, and is therefore related to the story, the terminology of the story is used.

"Variables" in the analytic model comprise what are known as "analytical parameters" and "parameters" in the analytical dataset.



<a name="loioa9950b0a7bc04fd1b9827800e67b26f1__section_sr2_whf_mvb"/>

## Attibutes and Dimensions

"Attributes” in the analytical dataset are known as “dimensions” in the analytic model.

